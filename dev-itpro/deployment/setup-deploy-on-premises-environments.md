---
title: "Ställ in och distribuera lokala miljöer"
description: "Det här avsnittet innehåller information om hur du planerar, konfigurerar och distribuerar en lokal miljö."
author: sarvanisathish
manager: AnnBe
ms.date: 08/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Operations, Unified Operations
ms.search.region: Global
ms.author: sarvanis
ms.search.validFrom: 2017-06-30T00:00:00.000Z
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: d100f6dbcbdf8f4c12ab04670fb598a88d48d84b
ms.openlocfilehash: 7caf033ab2de5afd6a2d88fa2d41631df4542cbe
ms.contentlocale: sv-se
ms.lasthandoff: 08/10/2017

---

# <a name="set-up-and-deploy-on-premises-environments"></a>Ställ in och distribuera lokala miljöer

Det här dokumentet beskriver hur du planerar distributionen, ställer in infrastrukturen och distribuerar Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (lokal).

## <a name="finance-and-operations-components"></a>Finance and Operations, komponenter

Finance and Operations-programmet består av tre huvudkomponenter:

- Programobjektserver (AOS)
- Business Intelligence (BI)
- Ekonomisk rapportering/Management Reporter

Dessa komponenter är beroende av följande systemprogramvara:

- Microsoft Windows Server 2016
- Microsoft SQL Server 2016 SP1, som innehåller följande funktioner:

    - Fulltextindexsökning är aktiverad.
    - SQL Server Reporting Services (SSRS).
    - SQL Server Integration Services (SSIS).
    
     > [!NOTE]
     > Programmet kan inte köras om fullständig textsökning inte är aktiverad.

- SQL Server Management Studio
- Fristående Microsoft Azure Service Fabric
- Windows PowerShell 5.0 eller senare
- Active Directory Federation Services (AD FS) i Windows Server 2016

  Domänkontrollanten måste vara Windows Server 2012 R2 eller senare med domänfunktionsnivån 2012 R2 eller större

  Mer information om domänfunktionsnivåer finns i: 
  - [Vad är funktionsnivåer i Active Directory](https://technet.microsoft.com/en-us/library/cc787290(v=ws.10).aspx)
  - [Förstå funktionsnivåer i Active Directory domäntjänster](https://technet.microsoft.com/en-us/library/understanding-active-directory-functional-levels(v=ws.10).aspx)


## <a name="lifecycle-services"></a>Lifecycle Services

Finance and Operations bitar distribueras via Microsoft Dynamics Lifecycle Services (LCS). Innan du kan distribuera måste du köpa licensnycklar via kanalen [Enterprise-avtal](https://www.microsoft.com/en-us/Licensing/licensing-programs/enterprise.aspx) och ställa in ett lokalt projekt i LCS. Distributioner kan endast initieras via LCS. Mer information om hur du ställer in lokala projekt i LCS finns i [Skapa ett lokalt projekt i Lifecycle Services](../lifecycle-services/lbd-create-lcs-on-prem-project.md).

## <a name="authentication"></a>Äkthetsbevisning

Det lokala programmet fungerar med AD FS. Du måste konfigurera Azure Active Directory (AD Azure) för att kunna arbeta med LCS.

## <a name="standalone-service-fabric"></a>Fristående Service Fabric

Finance and Operations använder fristående Service Fabric. Mer information finns i [Service Fabric-dokumentationen](/azure/service-fabric/).

## <a name="infrastructure"></a>Infrastruktur

Finance and Operations är utformade att fungera med en mycket sammanslagen arkitektur. Maskinvarukonfigurationen innehåller följande komponenter:

- Fristående gruppering med Service Fabric bygger på Windows Server 2016 virtuella datorer (VMs)
- SQL Server (både Grupperad SQL och Alltid på stöds)
- AD FS för autentisering
- Server Message Block (SMB) version 3 filresurs för lagring
- Tillval: Microsoft Office Server 2017

Mer information finns i [Systemkrav](../get-started/system-requirements.md) och storleksriktlinjer.

### <a name="hardware-layout"></a>Layout för maskinvara

Planera din infrastruktur och Service Fabric-gruppering, baserat på den rekommenderade storleken i [Maskinvarustorlek för lokala miljöer](../get-started/hardware-sizing-on-premises-environments.md). För mer information om hur du planerar Service Fabric-grupperingen, se [Planera och förbereda distributionen av fristående Service Fabric-gruppering](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

Tabellen nedan visar ett exempel maskinvarulayouten. Detta exempel används genom detta ämne för att illustrera inställningarna.

> [!NOTE]
> Den primära noden i Service Fabric-grupperingen måste ha minst tre noder. I det här exemplet anges **OrchestratorType** som den primära nodtypen.

| Syftet med datorn                                 | Datornamn    | IP-adress    |
|-------------------------------------------------|-----------------|---------------|
| Domänkontrollant                               | DAX7SQLAODC1    | 10.179.108.2  |
| AD FS                                           | DAX7SQLAOADFS1  | 10.179.108.3  |
| Filserver                                     | DAX7SQLAOFILE1  | 10.179.108.4  |
| SQL Alltid på-grupperingen                           | DAX7SQLAOSQLA01 | 10.179.108.5  |
|                                                 | DAX7SQLAOSQLA02 | 10.179.108.6  |
|                                                 | DAX7SQLAOSQLA   | 10.179.108.9  |
| Kund                                          | SQLAOCLIENT1    | 10.179.108.11 |
| Service Fabric-gruppering/AOS 1                    | SQLAOSF1AOS1    | 10.179.108.12 |
| Service Fabric-gruppering/AOS 2                    | SQLAOSF1AOS2    | 10.179.108.13 |
| Service Fabric-gruppering/AOS 3                    | SQLAOSF1AOS3    | 10.179.108.14 |
| Service Fabric-gruppering/Orchestrator 1           | SQLAOSF1ORCH1   | 10.179.108.15 |
| Service Fabric-gruppering/Orchestrator 2           | SQLAOSF1ORCH2   | 10.179.108.16 |
| Service Fabric-gruppering/Orchestrator 3           | SQLAOSF1ORCH3   | 10.179.108.17 |
| Service Fabric-gruppering/Styrningsrapporteringsnod | SQLAOSMR1       | 10.179.108.18 |
| Service Fabric-gruppering/SSRS-nod                | SQLAOSFBIN1     | 10.179.108.10 |

## <a name="setup"></a>Inställningar

### <a name="prerequisites"></a>Förutsättningar

Följande förutsättningar måste vara uppfyllda innan du startar installationen. Inställningen av dessa förutsättningarna är utanför detta dokumentets omfattning.

- Active Directory Domain Services (AD DS) har installerats och konfigurerats i nätverket.
- ADFS distribueras.
- SQL Server, SSRS och Management Studio har installerats.

### <a name="overview"></a>Översikt

Följande steg måste slutföras om du vill konfigurera infrastrukturen för Finance and Operations.

1. Planera ditt domännamn och DNS-zoner
2. Planera och hämta certifikat
3. Planera dina användare och tjänstkonton
4. Skapa DNS-zoner och lägg till A-poster
5. Anslut virtuella maskiner till domänen
6. Lägg till förutsättningsprogram till virtuella maskiner
7. Hämta installationsskript från LCS
8. Beskriv konfigurationen
9. Installera alla certifikat
10. Ställ in fristående Service Fabric-gruppering
11. Konfigurera LCS-anslutning för innehavaren
12. Ställ in fillagring
13. Ställ in SQL Server
14. Konfigurera databaserna
15. Kryptera autentiseringsuppgifter
16. Ställ in SSRS
17. Konfigurera AD FS

### <a name="plan-your-domain-name-and-dns-zones"></a>Planera ditt domännamn och DNS-zoner

Vi rekommenderar att du använder ett offentligt domännamn för produktionsinstallationen av AOS. På så sätt kommer du åt det utanför nätverket, om åtkomst utanför krävs.

Exempelvis om företagets domän är contoso.com kan dinzon för Finance and Operations (lokalt) vara d365ffo.onprem.contoso.com och värdnamnen kan ha följande värden:

- ax.d365ffo.onprem.contoso.com för AOS-datorer
- sf.d365ffo.onprem.contoso.com för Service Fabric-gruppering

### <a name="plan-and-acquire-your-certificates"></a>Planera och hämta certifikat

SSL-certifikat (Secure Sockets Layer) krävs för att skydda en Service Fabric-gruppering och alla program som installeras. För dina arbetsbelastningar för produktion och begränsat läge rekommenderar vi att du förvärvar certifikat från en certifikatutfärdare (CA) som t.ex. [DigiCert](https://www.digicert.com/ssl-certificate/), [Comodo](https://ssl.comodo.com/), [Symantec](https://www.websecurity.symantec.com/ssl-certificate), [GoDaddy](https://www.godaddy.com/web-security/ssl-certificate), eller [GlobalSign](https://www.globalsign.com/en/ssl/). Om domänen har konfigurerats med [Active Directory Certificate Services](https://technet.microsoft.com/en-us/library/cc772393(v=ws.10).aspx) (AD CS) kan du skapa certifikat via Active Directory-certifikattjänster. Varje certifikat måste innehålla en privat nyckel som har skapats för nyckelutbyte och måste därför kunna exporteras till en fil för Personal Information Exchange (PFX).

Självsignerade certifikat kan bara användas för testning. Skriptinställningar innehåller skript som genererar och exportera självsignerade certifikat. Som vi tidigare har nämnt används dessa certifikat i testsyfte.

| Syfte                                      | Förklaring | Ytterligare krav |
|----------------------------------------------|-------------|-------------------------|
| SQL Server SSL-certifikat                   | Certifikatet används för att kryptera data som skickas över ett nätverk mellan en instans av SQL Server och ett klientprogram. | <p>Domännamnet för certifikatet ska matcha det fullt kvalificerade domännamnet (FQDN) för SQL Server-instansen eller lyssnaren.</p><p>Om SQL-lyssnaren t.ex. finns på datorn DAX7SQLAOSQLA, är certifikatets DNS-namn DAX7SQLAOSQLA.onprem.contoso.com.</p> |
| Service Fabric Server-certifikat            | Certifikatet används för att skydda kommunikationen mellan noderna Service Fabric-noderna. Certifikatet används också som servercertifikatet som presenteras för klienter som ansluter till klustret. | <p>Domännamnet för certifikatet måste matcha DNS-zonen där AOS och Service Fabric finns.</p><p>Domännamnet för certifikatet kan till exempel vara \*.onprem.contoso.com or \*.contoso.com.</p><p>Om du använder ett jokerteckencertifikat gäller jokertecknet endast en nivå. En underdomän, alternativt ämnesnamn (SAN) måste tillämpas på certifikatet om det är flera nivåer t.ex. \*.contoso.com i föregående exempel.</p> |
| Service Fabric klient-certifikat            | Certifikatet används av klienter för att visa och hantera Service Fabric-klustret. | |
| Chiffreringcertifikat                     | Certifikatet används för att kryptera känslig information, som till exempel SQL Server-lösenord och lösenord för användarkonton. | <p>Certifikatnyckelanvändning måste innehålla datachiffrering (10) och får inte innehålla serverautentisering och klientautentisering.</p><p>Mer information finns i [hantering av hemligheterna i Service Fabric-program](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-application-secret-management).</p> |
| AOS SSL-certifikat                          | <p>Certifikatet används också som servercertifikatet som presenteras för klienter för AOS-webbplatsen. Den används också för att aktivera Windows Communication Foundation (WCF)/Simple Object Access Protocol (SOAP)-certifikat.</p><p>Service Fabric Server-certifikatet kan användas här om det är ett jokerteckencertifikat.</p> | <p>Domännamnet för certifikatet måste matcha DNS-zonen där AOS och Service Fabric finns.</p><p>Domännamnet för certifikatet kan till exempel vara \*.d365ffo.onprem.contoso.com, \*.onprem.contoso.com, eller \*.contoso.com.</p><p>Om du använder ett jokerteckencertifikat gäller jokertecknet endast en nivå. En underdomän (SAN) måste tillämpas på certifikatet om det är flera nivåer t.ex. \*.contoso.com i föregående exempel.</p> |
| Sessionsidentifieringscertifikat           | Certifikatet används av AOS för att skydda användarens sessionsinformation. | Detta är också det **fildelnings**-certifikat som används i distributionen från LCS. |
| Certifikat för kryptering och signering av data | Certifikaten används av AOS för att kryptera känslig information. | |
| Klientcertifikat för ekonomisk rapportering       | Certifikatet används för att skydda kommunikationen mellan ekonomiska rapporteringstjänster och AOS. | |
| Rapporteringscertifikat                        | Certifikatet används för att skydda kommunikationen mellan SSRS och AOS. | |
| Lokalt agentcertifikat           | <p>Certifikatet används för att skydda kommunikationen mellan ett lokalt ombud som finns lokalt och LCS.</p><p>Det här certifikatet låter den lokala agenten fungera som ombud i Azure AD-innehavare och kommunicera med LCS för att leda och övervaka distributioner.</p> | |

### <a name="plan-your-users-and-service-accounts"></a>Planera dina användare och tjänstkonton

Du måste skapa flera användar- eller tjänstkonton för att Finance and Operations (lokal) ska fungera. Du måste skapa en kombination av SQL-konton, domänkonton och grupphanterade tjänstkonton (gMSAs). Följande tabell visar användarkonton, syfte och exempel på namn som ska användas i det här avsnittet.

| Användarkonton                                            | Typ           | Syfte | Användarnamn |
|---------------------------------------------------------|----------------|---------|-----------|
| Programtjänstkonto för ekonomisk rapportering         | gMSA           |         | Contoso\\svc-FRAS$ |
| Processtjänstkonto för ekonomisk rapportering             | gMSA           |         | Contoso\\svc-FRPS$ |
| Designertjänstkonto för ekonomisk rapportering med ett klick | gMSA           |         | Contoso\\svc-FRCO$ |
| AOS tjänstkonto                                     | gMSA           | Den här användaren ska skapas för korrektur i framtiden. Vi planerar att AOS ska fungera med gMSA i kommande versioner. Du kan garantera en sömlös övergång till gMSA genom att skapa användaren vid tidpunkten för installationen. | Contoso\\svc-AXSF$ |
| AOS tjänstkonto                                     | Domänkonto | Den använder den här användaren i GA-versionen. | Contoso\\AXServiceUser |
| Administratörsanvändare AOS SQL DB                                   | SQL-användare       | Finance and Operations använder denna användare vid autentisering med SQL\*. Användaren ska också ersättas av gMSA-användaren i kommande versioner. | AXDBAdmin |
| Agenttjänstkonto lokal distribution                  | gMSA           | Detta konto används av lokala agenten för att leda distributionen på olika noder. | Contoso\\Svc LocalAgent$ |

\*SQL-användarnamnet och lösenordet för SQL-autentisering är säker eftersom den krypteras och lagras i den delade filresursen.

### <a name="create-dns-zones-and-add-a-records"></a>Skapa DNS-zoner och lägg till A-poster

DNS är integrerad med AD DS och låter dig organisera, hantera och hitta resurser i ett nätverk. Skapa en DNS-zon för framåtsökning och A-poster för AOS-värdnamnet och Service Fabric-klustret. I de här exempelinställningarna är DNS-zonnamnet d365ffo.onprem.contoso.com och A-poster/värdnamn är följande:

- **ax**.d365ffo.onprem.contoso.com för AOS-maskiner
- **sf**.d365ffo.onprem.contoso.com för Service Fabric-kluster

#### <a name="add-a-dns-zone"></a>Lägg till en DNS-zon

Gör på följande sätt för att lägga till en DNS-zon.

1. Logga in på domainkontrollmaskine, klicka på **starta** och starta DNS-hanteraren genom att skriva **dnsmgmt.msc**.
2. Högerklicka på domänkontrollantnamnet och klicka sedan på **Ny zon** \> **Nästa**.
3. Välj **primär zon**.
4. Lämna kryssrutan **Spara zonen i Active Directory (endast tillgängligt om DNS-servern är en skrivbar domänkontrollant** markerad och klicka sedan på **nästa**.
5. Välj **till alla DNS-servrar som körs på domänkontrollanter i domänen: Contoso.com**, och klicka sedan på **nästa**.
6. Välj **Zoner för framåtsökning**, och klicka sedan på **nästa**.
7. Ange zonnamnet för installationen och klicka sedan på **nästa**. Ange t.ex. **d365ffo.onprem.contoso.com**.
8. Välj **Tillåt inte dynamisk uppdatering**, och klicka sedan på **nästa**.

#### <a name="set-up-an-a-record-for-aos"></a>Ange en A-post för AOS

I den nya DNS-zonen, skapa en A-post som heter **ax.d365ffo.onprem.contoso.com** för **varje** Service Fabric-klusternod på typen **AOSNodeType**. Skapa inte A-poster för andra nodtyper.

1. Högerklicka på den nya zonen och klicka sedan på **Ny värd**.
2. Ange namn och IP-adressen för Service Fabric-noden (t.ex. 10.179.108.12) och klicka sedan på **Lägg till värd**.

#### <a name="set-up-an-a-record-for-the-orchestrator"></a>Ange en A-post för orchestrator

I den nya DNS-zonen, skapa en A-post som heter **sf.d365ffo.onprem.contoso.com** för **varje** Service Fabric-klusternod på typen **OrchestratorType**. Skapa inte A-poster för andra nodtyper.

1. Högerklicka på den nya zonen och klicka sedan på **Ny värd**.
2. Ange namn och IP-adressen för Service Fabric-noden (t.ex. 10.179.108.15) och klicka sedan på **Lägg till värd**.

#### <a name="join-vms-to-the-domain"></a>Anslut virtuella maskiner till domänen

Anslut var och en av de virtuella maskinerna till domänen genom att utföra stegen i [hur du ansluter Windows Server 2016 till Active Directory-domänen](http://www.tomsitpro.com/articles/join-windows-server-2016-to-ad-domain,2-1063.html). Du kan också använda Windows PowerShell-skript.

```
$domainName = Read-Host -Prompt 'Specify domain name (ex: contoso.com)'
Add-Computer -DomainName $domainName -Credential (Get-Credential -Message 'Enter domain credential')
Restart-Computer
```
När de virtuella maskinerna är anslutna till domänen, lägg till tjänstekonton för AOS (Contoso\svc-AXSF$ , Contoso\svc-AXSF$ ) till den lokala administratörsgruppen. Du kan kontrollera [lägg till en medlem i gruppen](https://technet.microsoft.com/en-us/library/cc772524(v=ws.11).aspx)-artikeln hur du gör detta.

#### <a name="disable-user-access-control"></a>Inaktivera användaråtkomstkontroll 

Kör följande skript om du vill inaktivera användaråtkomstkontroll **varje** Service Fabric-nod.
```
$RegPath = "HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System"
New-ItemProperty -Path $RegPath -Name "EnableLUA" -Value 0 -PropertyType "DWORD" -Force
New-ItemProperty -Path $RegPath -Name "ConsentPromptBehaviorAdmin" -Value 0 -PropertyType "DWORD" -Force
New-ItemProperty -Path $RegPath -Name "EnableUIADesktopToggle" -Value 0 -PropertyType "DWORD" -Force
New-ItemProperty -Path $RegPath -Name "LocalAccountTokenFilterPolicy" -Value 1 -PropertyType "DWORD" -Force
```
> [!IMPORTANT]
> Du måste starta om noden när skriptet har körts.

#### <a name="add-prerequisite-software-to-vms"></a>Lägg till förutsättningsprogram till virtuella maskiner

Tabellen nedan innehåller programvara som tillämpas för maskiner för varje nodtyp.

> [!NOTE]
> Du måste starta om datorn när du installerar komponenterna.

| Nodtyp | Komponent | Kommando |
|-----------|-----------|---------|
| AOS       | SNAC – ODBC-drivrutin | Se [Microsoft ODBC drivrutin 13.1 för SQL Server - Windows + Linux](https://www.microsoft.com/en-us/download/details.aspx?id=53339). |
| AOS       | Microsoft .NET Framework version 2.0–3.5 (CLR 2.0) | `Add-WindowsFeature -Name NET-Framework-Features, NET-Framework-Core, NET-HTTP-Activation, NET-Non-HTTP-Activ` |
| AOS       | Microsoft .NET Framework version 4.0–4.6 (CLR 4.0) | `Add-WindowsFeature -Name NET-Framework-45-Features, NET-Framework-45-Core, NET-Framework-45-ASPNET, NET-WCF-Services45, NET-WCF-TCP-PortSharing45` |
| AOS       | Internet Information Services (IIS) | `Add-WindowsFeature WAS, WAS-Process-Model, WAS-NET-Environment, WAS-Config-APIs`<br>`# Windows Process Activation Service`<br>`Add-WindowsFeature Web-Server, Web-WebServer, Web-Security, Web-Filtering, Web-App-Dev, Web-Net-Ext, Web-Mgmt-Tools, Web-Mgmt-Console` |
| AOS       | Microsoft SQL Server Management Studio 2016 | |
| AOS       | Microsoft Visual C++ omdistribuerbart paket för Microsoft Visual Studio 2013 | Se [Microsoft Visual C++ omdistribuerbart paket för Microsoft Visual Studio 2013](https://support.microsoft.com/en-us/help/3179560). |
| AOS       | Microsoft Access Database Engine 2010 omdistribuerbart  | Se [Microsoft Access Database Engine 2010 omdistribuerbart](https://www.microsoft.com/en-us/download/details.aspx?id=13255) |
| BI        | .NET Framework version 2.0–3.5 (CLR 2.0) | `Add-WindowsFeature -Name NET-Framework-Features, NET-Framework-Core, NET-HTTP-Activation, NET-Non-HTTP-Activ` |
| BI        | .NET Framework version 4.0–4.6 (CLR 4.0) | `Add-WindowsFeature -Name NET-Framework-45-Features, NET-Framework-45-Core, NET-Framework-45-ASPNET, NET-WCF-Services45, NET-WCF-TCP-PortSharing45` |
| BI        | Microsoft SQL Server 2016 SP1 | |
| BI        | Management Studio 2016 | |
| BI        | SQL Server Reporting Services 2016 i läget **intern** | |
| MR        | .NET Framework version 2.0–3.5 (CLR 2.0) | `Add-WindowsFeature -Name NET-Framework-Features, NET-Framework-Core, NET-HTTP-Activation, NET-Non-HTTP-Activ` |
| MR        | .NET Framework version 4.0–4.6 (CLR 4.0) | `Add-WindowsFeature -Name NET-Framework-45-Features, NET-Framework-45-Core, NET-Framework-45-ASPNET, NET-WCF-Services45, NET-WCF-TCP-PortSharing45` |
| MR        | Visual C++ omdistribuerbart paket för Microsoft Visual Studio 2013 | Se [Microsoft Visual C++ omdistribuerbart paket för Microsoft Visual Studio 2013](https://support.microsoft.com/en-us/help/3179560). |

#### <a name="download-setup-scripts-from-lcs"></a>Hämta installationsskript från LCS

Vi har samlat ett antal skript för att förbättra installationsförloppet. Följ instruktionerna om du vill hämta inställningsskript från LCS.

1. Logga in på LCS (<https://lcs.dynamics.com/v2>).
2. På instrumentpanelen, klicka på panelen **delat resursbibliotek**.
3. Klicka på fliken **Modell**.
4. I rutmönstret väljer du raden **Dynamics 365 for Operations - Distributionsskript lokal**.
5. Klicka på **versioner**, och hämta den senaste versionen av skripten.

### <a name="describe-your-configuration"></a>Beskriv konfigurationen

Det här avsnittet innehåller information om de skript du måste köra. Skripten behandlas i den ordning som du måste köra dem i. Om du vill köra skripten fyller i du i mallfilen vid $(downloadPath)\\ConfigTemplate.xml. Filen ConfigTemplate.xml beskriver Service Fabric-kluster, certifikatet som används för att konfigurera dem och de konton du måste ha åtkomst till för de relevanta certifikaten. I exemplet som anges fylls värden i, exemplet infrastruktur, som beskrivs i det här avsnittet. Mallfilen används i nästa avsnitt.

#### <a name="create-the-domain-account-for-a-service-user"></a>Skapa domänkontot för serviceanvändare

Kör följande kommando för att skapa domänanvändarkonto contoso\\AXServiceUser.

```
New-ADUser -Name 'AXServiceUser' `
    -AccountPassword (Read-Host -Prompt 'Specify User Password' -AsSecureString) `
    -PasswordNeverExpires $true -ChangePasswordAtLogon $false `
    -Enabled $true -UserPrincipalName 'AXServiceUser@contoso.com'
```

#### <a name="create-gmsas"></a>Skapa gMSAs

1. Ändra katalogen till **$(DownloadPath)**, och kör följande kommando för Windows PowerShell.

    > [!NOTE]
    > Det här skriptet skapar inte användarna. Det skriver istället ut kommandona manuellt som måste köras på domainkontrollmaskinen.

    ```
    # Generate gMSA account creation script (shows in console):
    .\Get-NewGMSAInDomainScript.ps1 -InputXml .\ConfigTemplate.xml
    ```

2. Kopiera resultatet av kommandot till Windows PowerShell-fönstret. Se till att radbrytningarna tas bort och köra raderna på Active Directory domainkontrollmaskinen med utökad behörighet (högerklicka och klicka sedan på **kör som administratör**).
3. Kör följande skript på Active Directory domainkontrollmaskinen för att validera att kontona har skapats. Kontrollera att du kör skriptet efter att du byter ut mönstret som matchar namngivningen av tjänstkonton.

    ```
    #Use this command to validate the gMSA accounts are added to AD.
    #Ensure to replace the Filter parameter with the pattern used to create your accounts.
    Get-ADServiceAccount -Filter { samAccountName -like "svc-*" }
    ```

4. Kör skriptet Export AddGMSAsONVMScript.ps1 på klientdatorn. Skriptet skapar skript som körs på varje Service Fabric-VM och lägger till dem i en mapp som motsvarar varje VM-namn.

    ```
    # Exports a script for installing gMSA on VM nodes into a directory VMs\<VMName>, again feed from XML
    .\Export-AddGMSAsOnVMScript.ps1 -InputXml .\ConfigTemplate.xml
    ```

#### <a name="stop-iis"></a>Stoppa IIS

Använd RDP-protokollet (Remote Desktop Protocol) för att ansluta till varje Service Fabric-VM och slutför stegen i [starta eller stoppa webbserver (IIS 7)](https://technet.microsoft.com/en-us/library/cc732317(v=ws.10).aspx). Du kan också använda följande Windows PowerShell-skript med RDP för att ansluta till varje Service Fabric-VM.

```
$ServiceName = "WAS"
$wasService = Get-Service $ServiceName -ErrorAction SilentlyContinue
if($wasService)
{
    $wasService.DependentServices | Stop-Service -Force -ErrorAction Continue
    $wasService | Stop-Service -ErrorAction Continue
    Set-Service $ServiceName -StartupType Disabled
}

$ServiceName = 'W3SVC'
$w3svc = Get-Service $ServiceName -ErrorAction SilentlyContinue
if($w3svc)
{
    $w3svc.DependentServices | Stop-Service -Force -ErrorAction Continue
    $w3svc | Stop-Service -ErrorAction Continue
    Set-Service $ServiceName -StartupType Disabled
}
```
_IIS-funktionen ska installeras men inaktiveras eftersom det finns några beroenden för IIS dlls i produkten._

### <a name="install-certificates"></a>Installera certifikat

1. Om du har köpt de certifikat som beskrevs tidigare i det här avsnittet från en giltig certifikatutfärdare fyller du i PFX-filens namn och stämpel för certifikatet som finns i filen ConfigTemplate.xml. Ange attributet **generateSelfSignedCert** till **falsk** och attributet **kan exporteras** till **falsk**. Kopiera .pfx-filer till $(DownloadPath)\\InfrastructureScripts\\certifikat-mappen.
2. Kör följande skript om du använder självsignerade certifikat (endast för testning). Skapa självsignerade certifikat i filen ConfigTemplate.xml genom att **generateSelfSignedCert** anges till **sant** och **kan exporteras** anges till **sant**. Skriptet uppdaterar XML med tumavtryck för certifikat.

    ```
    # Create self-signed certs (optionally, use -Display if you only want to see commands):
    # Note: this script is completely driven off ConfigTemplate.xml
    .\New-SelfSignedCertificates.ps1 -InputXml .\ConfigTemplate.xml
    ```

3. Exportera nya certifikat med privat nyckel (.pfx-fil). Använd följande skript för att skapa och köra exportkommandot i Windows PowerShell. .pfx-filer placeras i certifikatmappen.

    ```
    # Exports Pfx files into a directory VMs\<VMName>, all the certs will reside in a folder named Certs\
    # Feeds from XML, if certs don't have passwords then you are prompted to enter one
    .\Export-PfxFiles.ps1 -InputXml .\ConfigTemplate.xml
    ```

    > [!NOTE]
    > Certifikaten måste vara installerade och måste finnas i cert:\\CurrentUser\\My. Certifikat måste också kunna exporteras.

    Om du använder självsignerade certifikat går du vidare till nästa avsnitt. Du har inte behörighet att slutföra den här processen.

4. När du exporterar eller kopierar .pfx-filer till $(DownloadPath)\\InfrastructureScripts\\certifikatmapp, kör följande kommandon för att generera skript som ska placeras i mappen som motsvarar de virtuella maskiner.

    ```
    # Exports script for adding ACLs to certs into a directory VMs\<VMName>
    .\Export-CertificateAclsForVMs.ps1 -InputXml .\ConfigTemplate.xml
    
    # Exports Import-PfxFiles.ps1 script for importing PFXs on VM nodes into a directory VMS\<VMname>:
    .\Export-ImportPfxFilesScript.ps1 -InputXml .\ConfigTemplate.xml
    
    .\Export-UnblockStrongNameScript.ps1 -InputXml .\ConfigTemplate.xml
    ```

5. Kopiera skript i varje mapp till VMs som motsvarar mappnamnet.
6. Kör följande skript i den ordning som de förekommer i varje VM.

    ```
    #Run this script only if it exists
    .\Add-GMSAOnVM.ps1
    
    .\Import-PfxFiles.ps1
    
    .\Set-CertificateAcls.ps1
    
    #Run this script only if it exists
    .\Unblock-StrongName.ps1
    ```

### <a name="set-up-a-standalone-service-fabric-cluster"></a>Ställ in fristående Service Fabric-kluster

1. Kör följande kommando för att generera filen ClusterConfig.json.

    ```
    .\New-SFClusterConfig.ps1 -InputXml .\ConfigTemplate.xml
    ```

    Mer information finns i [steg 1B: skapa ett kluster med flera maskiner](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-cluster-creation-for-windows-server#create-the-cluster), [säkra ett fristående kluster på Windows med X.509-certifikat](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-windows-cluster-x509-security), och [skapa ett fristående kluster som körs på Windows Server](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-cluster-creation-for-windows-server#create-the-cluster).

2. Hämta [Service Fabric fristående installationspaket](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-cluster-creation-for-windows-server#download-the-service-fabric-standalone-package) till en Service Fabric-nod. När zip-filen har hämtats avblockera den genom att högerklicka på zip-filen och sedan **egenskaper**. I dialogrutan markerar du kryssrutan **Avblockera** i det nedre högra hörnet.
3. Kopiera zip-filen till en av noderna i Service Fabric-klustret och packa upp den.
4. Kör följande kommandon för att skapa en brandväggsregel för inkommande trafik på port 443 och 445 på alla noder.

    ```
    #Create inbound Rule
    New-NetFirewallRule -DisplayName "SFInbound443445" -LocalPort 135, 137, 138, 139, 445, 443 -Direction Inbound -Enabled True -Protocol TCP
    
    #Test inbound Rule
    Get-NetFirewallRule -DisplayName "SFInbound443445"
    ```

5. Kör följande kommandon för att skapa en brandväggsregel för inkommande trafik på port 80, endast för SSRS-nod.

    ```
    #Create inbound Rule
    New-NetFirewallRule -DisplayName "Reporting80" -LocalPort 80 -Direction Inbound -Enabled True -Protocol TCP
    
    #Test inbound Rule
    Get-NetFirewallRule -DisplayName "Reporting80"
    ```

6. Kopiera filen ClusterConfig.json till ouppackade installationsplatsen för fristående Service Fabric.
7. Navigera till ouppackade installationsplatsen i Windows PowerShell med förhöjd behörighet och kör följande kommando för att testa ClusterConfig.

    ```
    .\TestConfiguration.ps1 -ClusterConfigFilePath .\clusterConfig.json
    ```

8. Kör följande kommando för att distribuera klustret om testet lyckas.

    ```
    .\CreateServiceFabricCluster.ps1 -ClusterConfigFilePath .\ClusterConfig.json
    ```

9. Öppna Service Fabric-utforskaren på en klientdator för att verifiera installationen när du har skapat klustret:

    1. Installera Service Fabric-klientcertifikatet i CurrentUser\\My om den inte redan är installerad.
    2. Gå till **IE-inställningar** \> **kompatibilitetsläge**, och avmarkera kryssrutan **visa intranätplatser i kompatibilitetsläge**.
    3. Gå till `https://sf.d365ffo.onprem.contoso.com:19080`, där sf.d365ffo.onprem.contoso.com är värdnamnet för Service Fabric-klustret som anges i zonen. Om DNS-namnmatchning inte är konfigurerad, använd IP-adressen för datorn.
    4. Välj klientcertifikat. Sian **Service Fabric-utforskaren** visas.

### <a name="configure-lcs-connectivity-for-the-tenant"></a>Konfigurera LCS-anslutning för innehavaren

Distribution och underhåll av Finance and Operations sköts av LCS genom att använda en lokal agent. Om du vill skapa anslutningen från LCS till Finance and Operations-innehavare måste du konfigurera ett certifikat som möjliggör att den lokala agenten utföra arbete på din AD Azure-innehavare (exempelvis Contoso.Onmicrosoft.com).

Använd det lokala agentcertifikat som du köper från en certifikatutfärdare eller ett självsignerat certifikat som du skapade med hjälp av skript.

Endast användarkonton som har katalogrollen Global administratör kan lägga till certifikat för att auktorisera LCS. Som standard blir den person som registrerar sig för Microsoft Office 365 för organisationens den globala administratören för katalogen.

> [!NOTE]
> Du måste konfigurera certifikatet exakt en gång per innehavare. Alla lokala miljöer kan använda samma certifikat för att ansluta till LCS.

1. Hämta och installera den senaste versionen av Azure PowerShell på en klientdator. Mer information finns i [installera och konfigurera Azure PowerShell](https://docs.microsoft.com/en-us/powershell/azure/install-azurerm-ps?view=azurermps-4.1.0&viewFallbackFrom=azurermps-4.0.0).
2. Logga in på [kundens Azure-portal](https://portal.azure.com) för att kontrollera att du har katalogrollen global administratör.
3. Kör följande skript från $(DownloadPath)\\InfrastructureScripts.

   ```
   .\AddCertToServicePrincipal.ps1 -CertificateThumbprint <OnPremLocalAgent Certificate Thumbprint>
   ```

### <a name="set-up-file-storage"></a>Ställ in fillagring

Du måste ställa in två högtillgängliga SMB 3.0 fildelningar. Information om hur du aktiverar SMB 3.0 finns i [SMB säkerhetsförbättringar](https://technet.microsoft.com/en-us/library/dn551363(v=ws.11).aspx#BKMK_disablesmb1).
Säkra dialektförhandling kan inte identifiera eller förhindra nedgraderingar från SMB 2.0 eller 3.0 till SMB 1.0. På grund av detta och för att utnyttja SMB-krypteringens fulla kunskaper rekommenderar vi starkt att du inaktiverar SMB 1.0-servern

> [!NOTE]
> För att garantera att dina data skyddas i viloläge i din miljö, måste BitLocker-diskkryptering aktiveras på varje dator. Information om hur du aktiverar BitLocker finns i [BitLocker: hur du distribuerar Windows Server 2012 och senare](https://docs.microsoft.com/en-us/windows/device-security/bitlocker/bitlocker-how-to-deploy-on-windows-server).

- En filresurs som lagrar dokument som överförs till AOS (t.ex. \\\\DAX7SQLAOFILE1\\aos-storage).
- En filresurs som lagrar de senaste versions- och konfigurationsfilerna för att leda distributionen (t.ex. \\\\DAX7SQLAOFILE1\\agent))

    > [!NOTE]
    > Behåll den här filresursens sökväg så kort som möjligt för att undvika att överskrida den maximala sökvägslängden för filer som placeras i resursen.

1. Kör följande kommando på fildelningsmaskinen.

    ```
    Install-WindowsFeature -Name FS-FileServer -IncludeAllSubFeature -IncludeManagementTools
    ```
#### <a name="set-up-the-dax7sqlaofile1aos-storage-file-share"></a>Ställ in \\\\DAX7SQLAOFILE1\\aos-fildelningslagring

2. I serverhanteraren väljer du **fil- och lagringstjänster** \> **delningar**.
3. Klicka på **uppgifter** \> **ny resurs** att skapa en ny resurs med namnet **aos-lagring**.
4. Ge behörigheten **ändra** för varje dator i Service Fabric-klustret förutom **OrchestratorNodeType**.
5. Ge behörigheten **ändra** för användarens AOS-domänanvändare (contoso\\AXServiceUser) och gMSA (contoso\\svc-AXSF).

#### <a name="set-up-the-dax7sqlaofile1agent-file-share"></a>Ställ in \\\\DAX7SQLAOFILE1\\agent-fildelningslagring

6. Gå tillbaka tilI serverhanteraren väljer du **fil- och lagringstjänster** \> **delningar**.
7. Klicka på **uppgifter** \> **ny resurs** att skapa en ny resurs med namnet **agent**.
8. Ge behörigheten **fullständig kontroll** till gMSA-användaren för agenten för lokal distribution (contoso\\svc-LocalAgent$).

### <a name="set-up-sql-server"></a>Ställ in SQL Server

1. Installera SQL Server 2016 SP1 med hög tillgänglighet som SQL-kluster som inkluderar ett SAN Storage Area Network (SAN) eller i en Alltid på-konfiguration.  Kontrollera att **Databasmotor, rapporteringstjänster, fullständig textsökning** och **hanteringsverktyg** har installerats.
> [!NOTE]
> Kontrollera att SQL Alltid på ställs in enligt [Välj inledande datasynkroniseringssida (Gruppguiden Alltid på tillgänglighet)](https://docs.microsoft.com/en-us/sql/database-engine/availability-groups/windows/select-initial-data-synchronization-page-always-on-availability-group-wizards) och följ [att förbereda sekundära databaser manuellt](https://docs.microsoft.com/en-us/sql/database-engine/availability-groups/windows/select-initial-data-synchronization-page-always-on-availability-group-wizards#PrepareSecondaryDbs)
2. Kör SQL-tjänsten som en domänanvändare.
3. Skaffa ett SSL-certifikat från en certifikatutfärdare för att konfigurera Finance and Operations. Självsignerade certifikat kan skapas för testning.

**Självsignerade certifikat för grupperad SQL-instans**
   ```
   New-SelfSignedCertificate -CertStoreLocation "cert:\CurrentUser\My" -DnsName "DAX7SQLAOSQLA.contososqlao.com" -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider" -Subject "DAX7SQLAOSQLA.contososqlao.com"
   ```
**Självsignerade certifikat för Alltid på SQL-instans**
```
#https://www.derekseaman.com/2014/11/sql-2014-alwayson-ag-pt-13-ssl.html

# Create certificate for each SQL Node (i.e. 2 nodes = 2 certificates)
# Run script on each node
$computerName = $env:COMPUTERNAME.ToLower() 
$domain = $env:USERDNSDOMAIN.ToLower()
$listenerName = 'dax7sqlaosqla' 
$cert = New-SelfSignedCertificate -Subject "$computerName.$domain" -DnsName "$listenerName.$domain", $listenerName, $computerName -Provider 'Microsoft Enhanced RSA and AES Cryptographic Provider'

```
4. Med certifikat, följ instruktionerna i [hur du aktiverar SSL-kryptering för en instans av SQL Server med hjälp av Microsoft Management Console](https://support.microsoft.com/en-us/help/316898/how-to-enable-ssl-encryption-for-an-instance-of-sql-server-by-using-microsoft-management-console) för att konfigurera SSL på SQL Server.
5. Följ dessa steg för varje nod i klustret. Kontrollera att du gör ändringarna på den ej aktiva noden och växla över till den när ändringar har gjorts.

    1. Importera certifikatet till den lokala datorn\\My.
    2. Bevilja behörighet för certifikat till servicekontot som används för att köra SQL-tjänsten. I Microsoft Management Console (MMC), högerklicka på certifikatet (certlm.msc) och klicka på **uppgifter** \> **hantera privata nycklar**.
    3. Lägg till tumavtryck för certifikat til\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Microsoft SQL Server\\*MSSQL.x*\\MSSQLServer\\SuperSocketNetLib\\-certifikat.
    4. I Microsoft SQL Server Configuration Manager, ange **ForceEncryption** till **Ja**.

6. Exportera den offentliga nyckeln för certifikatet (.cer-filen) och installera den i ett betrott rotcertifikat för varje Service Fabric-nod.

### <a name="configure-the-orchestratordata-database"></a>Konfigurera databasen OrchestratorData

1.  Skapa en tom databas och kalla den **OrchestratorData**. Den här databasen används av lokal agenten för att markera distributioner.
2.  Ge lokala agenten gMSA (svc-LocalAgent$) **db\_owner** behörigheter för databasen:

    1. Expandera servernamnet i konsolträdet, expandera **Säkerhet** \> **inloggningar**, och högerklicka sedan och på **Ny inloggning**.

        ![Kommandot Ny inloggning](./media/OPSetup_01_NewLogin.png)


    2. Leta upp tjänstkontot **svc LocalAgent$**. Klicka på **platser** och välj **hela katalogen**, och klicka sedan på **objekttyper**, och välj **tjänstekonto**.

        ![Välj dialogrutan användare, tjänstkonto eller grupp](./media/OPSetup_02_SelectUserServiceAccountOrGroupDialogBox.png)

    3. Ange **tilldela ServerRole** till **offentlig**.
    4. Tilldela databasrollbehörighet **db\_owner** till OrchestratorData-databasen.

### <a name="configure-the-finance-and-operations-database"></a>Konfigurera databasen Finance and Operations.

1. Logga in på LCS (<https://lcs.dynamics.com/v2>).
2. På instrumentpanelen, klicka på panelen **delat resursbibliotek**.
3. Klicka på fliken **Modell**. 
4. I rutnätet klickar du på **Dynamics 365 for Operations lokal, Enterprise edition - demodata** för att hämta zip-filen.
5. Zip-filen innehåller tomma demodata-.bakfiler. Baserat på dina behov väljer du lämplig .bak-fil. Till exempel om du behöver demodata återställer du filen AxBootstrapDB_Demodata.bak. 
6. Återställ AxBootstrapDB_DemoData.bak-databasen.
7. Byta namn på databasen **AXDBRAIN**.
8. Kör följande frågor på den återställda databasen.

    ```
    ALTER DATABASE AXDBRAIN
    SET READ_COMMITTED_SNAPSHOT ON
    GO
    
    ALTER DATABASE AXDBRAIN
    SET ALLOW_SNAPSHOT_ISOLATION ON
    GO
    ```

4. Uppdatera databasfilerna:

    1. Högerklicka på databasen och välj sedan **Egenskaper**.
    2. Klicka på **filer** för att ändra filegenskaperna för databasen.
    3. I fältet **ursprunglig storlek (MB)** anger du ett värde som är mer än 5,120.

        ![Dialogrutan databasegenskaper](./media/OPSetup_03_DatabasePropertiesDialogBox.png)

    4. För **AXDBBuild\_Data**, anger du **öka automatiskt/Maximera** till **200** megabyte (MB).
    5. För **AXDBBuild\_Log**, anger du **öka automatiskt/Maximera** till **500** megabyte (MB).

        ![Ändra egenskaper för öka automatiskt](./media/OPSetup_04_ChangeAutogrowthDialogBox.png)

5. Skapa en ny användare med SQL-autentisering aktiverad (axdbadmin).
6. Följ instruktionerna nedan för att mappa användare och databasroller.

    | Användare             | Typ    | Databasroll |
    |------------------|---------|---------------|
    | SVC AXSF$        | gMSA    | db\_ägare     |
    | svc-LocalAgent$  | gMSA    | db\_ägare     |
    | SVC AXSF$        | gMSA    | db\_ägare     |
    | SVC AXSF$        | gMSA    | db\_ägare     |
    | axdbadmin        | SqlUser | db\_ägare     |

7. Ge svc-AXSF$-användaren och axdbadmin SQL användaråtkomst till följande roller i tempdb-databasen:

    - db\_datareader
    - db\_datawriter
    - db\_ddladmin

8. Kör följande Transact SQL (T-SQL)-kommandon i Management Studio:

    ```
    GRANT VIEW SERVER STATE TO axdbadmin
    GRANT VIEW SERVER STATE TO [contososqlao\svc-AXSF$]
    ```
9. Kör följande kommando.
```
.\Reset-DatabaseUsers.ps1 -DatabaseServer ‘<FQDN of the SQL server>’ -DatabaseName '<AX database name>'
```

### <a name="configure-the-financial-reporting-database"></a>Konfigurera databasen för ekonomisk rapportering

1.  Skapa en tom databas och kalla den **FinancialReporting**.
2.  Följ instruktionerna nedan för att mappa användare och databasroller.

    | Användare             | Typ | Databasroll |
    |------------------|------|---------------|
    | svc-LocalAgent$  | gMSA | db\_ägare     |
    | SVC AXSF$        | gMSA | db\_ägare     |
    | SVC AXSF$        | gMSA | db\_ägare     |

### <a name="encrypt-credentials"></a>Kryptera autentiseringsuppgifter

1. Installera chiffreringscertifikatet på varje klientdator i den lokala datorn\\Mina certifikatarkiv.
2. Ge den aktuella användaren läsbehörighet till den privata nyckeln för certifikatet.
3. Skapa filen Credentials.json såsom visas här.

    ```
    {
        "AosPrincipal": {
            "AccountPassword": "<encryptedDomainUserPassword>"
        },
        "AosSqlAuth": {
            "SqlUser": "<encryptedSqlUser>",
            "SqlPwd": "<encryptedSqlPassword>"
        }
    }
    ```

    - **AccountPassword** är det krypterade lösenordet för AOS-domänanvändare (contoso\\axserviceuser).
    - **SqlUser** är krypterad SQL-användaren (axdbadmin) som har åtkomst till databasen Finance and Operations (AXDBRAIN) och **SqlPassword** är det krypterade SQL-lösenordet.

4. Kopiera filen .json till filresursen SMB \\\\AX7SQLAOFILE1\\agent\\inloggningsuppgifter\\Credentials.json.
5. Uppdatera filen Credentials.json med krypterad värden.

    ```
    # Service fabric API to encrypt text and copy it to the clipboard.
    Invoke-ServiceFabricEncryptText -Text '<textToEncrypt>' -CertThumbprint '<DataEncipherment Thumbprint>' -CertStore -StoreLocation LocalMachine -StoreName My | clip
    ```

    1. Ersätt i Credentials.json, **\<encryptedDomainUserPassword\>** med det krypterade lösenordet.
    2. Ersätt **\<encryptedSqlUser\>** med krypterad Finance and Operation SQL-användaren.
    3. Ersätt **\<encryptedSqlPassword\>** med Finance and Operation SQL-lösenord.
    
### <a name="set-up-ssrs"></a>Ställ in SSRS

1.  Innan du kan börja, se till att förutsättningarna som nämns i början av detta avsnitt har installerats.
2.  Följ stegen för att [Konfigurera SQL Server Reporting Services för en lokal distribution](../analytics/configure-ssrs-on-premises.md)

### <a name="configure-ad-fs"></a>Konfigurera AD FS

Innan du kan slutföra den här proceduren måste AD FS distribueras på Windows Server 2016. Information om hur du distribuerar AD FS finns i [Deployment Guide Windows Server 2016 och 2012 R2 AD FS Deployment Guide](https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/deployment/windows-server-2012-r2-ad-fs-deployment-guide).

Finance and Operations kräver ytterligare konfigurering, förutom den färdiga standardkonfigureringen av AD FS. Windows PowerShell körs på en dator med AD FS-rolltjänsten i följande steg. Användarkontot måste ha tillräcklig behörighet att administrera AD FS. Användaren måste till exempel ha ett domänadministratörskonto.

1. Konfigurera AD FS-identifierare så att den matchar AD FS tokenutfärdare.

    ```
    $adfsProperties = Get-AdfsProperties
    Set-AdfsProperties -Identifier $adfsProperties.IdTokenIssuer
    ```

2. Du bör inaktivera Windows Integrated Authentication (WIA) för intranätautentiseringsanslutningar om du inte har konfigurerat AD FS för blandade miljöer. Mer information om hur du konfigurerar WIA så att den kan användas med AD FS finns i [konfigurera webbläsare för att kunna använda Windows Integrated Authentication (WIA) med AD FS](https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/operations/configure-ad-fs-browser-wia).

   ```
   Set-AdfsGlobalAuthenticationPolicy -PrimaryIntranetAuthenticationProvider FormsAuthentication, MicrosoftPassportAuthentication
   ```

3. För inloggning måste användarens e-postadress vara en godtagbar autentiseringsingång.

   ```
   Add-Type -AssemblyName System.Net
   $fdqn = ([System.Net.Dns]::GetHostEntry('localhost').HostName).ToLower()
   $domainName = $fdqn.Substring($fdqn.IndexOf('.')+1)
   Set-AdfsClaimsProviderTrust -TargetIdentifier 'AD AUTHORITY' -AlternateLoginID mail -LookupForests $domainName
   ```

För att AD FS ska lita på Finance and Operations för utbyte av autentisering måste olika programposter registreras i AD FS under en AD FS-programgrupp. Du kan använda följande skript för registreringen för att påskynda installationsprocessen och hjälpa till att reducera fel. Kopiera skriptet Publish-ADFSApplicationGroup.ps1 och D365FO-OP-katalogen på en dator som har AD FS-rolltjänsten installerad. Kör skriptet med hjälp av ett användarkonto, till exempel ett administratörskonto som har tillräcklig behörighet att administrera AD FS. Mer information om hur du använder skriptet finns i dokumentationen som anges i skriptet. Notera klientens ID-nummer som angetts i resultatet, eftersom du kommer att uppmanas om informationen i LCS i ett senare steg.

```
# Host URL is your DNS record\host name for accessing the AOS
.\Publish-ADFSApplicationGroup.ps1 -HostUrl 'ax.d365ffo.onprem.contoso.com'
```

AD FS-hanteringskonsolen bör likna illustrationen. För att öppna serverhanteraren klicka på **verktyg** \> **AD FS-hantering**, och sedan längst ned till vänster i trädvyn klickar du på **programgrupper**. Dubbelklicka på programgruppen om du vill se mer information.

![Egenskaper för Programgruppen](./media/OPSetup_05_ApplicatioGroupProperties.png)

Slutligen för en rimlighetskontroll för att se till att du har åtkomst till AD FS OpenID konfigurations-URL på en Service Fabric-nod för typen **AOSNodeType** genom att gå till `https://<adfs-dns-name>/adfs/.well-known/openid-configuration` i en webbläsare. Om du får ett meddelande om att webbplatsen inte är säker har du inte lagt till ditt AD FS SSL-certifikat till arkivet för betrodda rotcertifikatutfärdare. Det här steget beskrivs i distributionsguiden för AD FS. Om du kommer åt URL:en kommer en JSON-fil (JavaScript Object Notation) returneras med AD FS-konfigurationen och du ser är din AD FS-URL är betrodd.

Med detta är inställningen av infrastrukturen slutförd. I följande avsnitt beskrivs hur du navigerar till [LCS](https://lcs.dynamics.com) för att ställa in din anslutning och distribuera miljön för Dynamics 365 for Finance and Operations.

## <a name="configure-connector-and-install-on-premises-local-agent"></a>Konfigurera anslutning och installera lokal agent

1. Logga in på [LCS](https://lcs.dynamics.com/) och öppna lokalt genomföringsprojekt.
2. På hamburgermenyn, klicka på **Projektinställningar**.

    ![Projektinställningskommando](./media/OPSetup_06_ProjectSettings.png)

3. Klicka på **Lokala anslutningar**.
4. Klicka på **Lägg till** för att skapa en ny anslutning.
5. På fliken **Ställ in värdinfrastruktur**, hämta agentinstallationsprogram.

    ![Hämta knappen för agentinstallation på fliken Ställ in värdinfrastruktur.](./media/OPSetup_07_DownloadAgentInstaller.png)

6. Kontrollera att zip-filen är avblockerad. Högerklicka på filen, klicka på **egenskaper**, och välj sedan **avblockera**.
7. Packa upp agentinstallationsprogrammet på Service fabric-noden för **OrchestratorType**-typen.
8. På fliken **konfigurera agent** anger du konfigurationsinställningarna.
9. Spara konfigurationen och klicka sedan på **hämta konfigurationer** för att hämta konfigurationsfilen localagent-config.json.

    ![Hämta konfigurationsknappen på fliken Konfigurera agent](./media/OPSetup_08_DownloadConfigurations.png)

10. Kopiera filen localagent-config.json till datorn där agentinstallationspaketet finns.
11. Kör följande kommando i fönstret Kommandotolken genom att navigera till den mapp som innehåller agentinstallationsprogram.

    ```
    LocalAgentCLI.exe Install <path to config.json>
    ```

    > [!NOTE]
    > Användare som kör kommandot måste behörighet **db\_owner** för OrchestratorData-databasen.
    
12. Gå tillbaka till den lokala anslutningen i LCS när lokala agenten installeras.
13. På fliken **Validera inställningar**, klicka på **meddelande agent**-knappen. Detta kommer att testa LCS-anslutningen till din lokala agent. När anslutningen har upprättats kommer sidan att se ut som på bilden nedan.

     ![Validera agent](./media/ValidateAgent.PNG)

## <a name="deploy-your-dynamics-365-for-finance-and-operations-on-premises-environment"></a>Distribuera datormiljön Dynamics 365 for Finance and Operations (lokal)

1. Navigera till ett lokalt projekt i LCS, gå till **miljö**, **begränsat** och klicka på **konfigurera**
2. Markera din **miljötopologi** och gå igenom guiden för att initiera distributionen.
3. Lokala agenten hämtar begäran om distribution, startar distributionen och kommunicerar tillbaka till LCS när du är klar.

