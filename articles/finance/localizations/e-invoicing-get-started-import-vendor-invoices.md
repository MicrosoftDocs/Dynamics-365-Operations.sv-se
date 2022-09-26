---
title: Använd e-faktureringstjänsten för att importera leverantörsfakturor
description: I den här artikeln finns information om hur du importerar leverantörsfakturor med hjälp av e-faktureringstjänsten.
author: gionoder
ms.date: 09/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.custom: 97423,  ""intro-internal
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 0195dc528f2fe6bf62efbf03f8706ea90f4a4fc4
ms.sourcegitcommit: a5a4c45bb265758c6e5c3483c8552503b1799a89
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/16/2022
ms.locfileid: "9524756"
---
# <a name="use-the-electronic-invoicing-service-to-import-vendor-invoices"></a>Använd e-faktureringstjänsten för att importera leverantörsfakturor

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Det här ämnet innehåller information som hjälper dig att komma igång med att importera leverantörsfakturor med tjänsten e-fakturering. Här får du hjälp med konfigurationsstegen i Regulatory Configuration Services (RCS), Dynamics 365 Finance och Dynamics 365 Supply Chain Management som du måste följa för att ta emot elektroniska leverantörsfakturor från leverantörerna.

## <a name="set-up-vendor-invoice-import-in-rcs"></a>Konfigurera leverantörsfakturaimport i RCS
Så här ställer du in import av leverantörsfakturor i RCS:

1. Läs i listan över [allmänt tillgängliga funktioner för e-fakturering](e-invoicing-configuration-rcs.md#generally-available-features).
2. Välj och importera funktion för e-fakturering. För mer information, se [Importera en e-faktureringsfunktion från Microsofts konfigurationsleverantör](e-invoicing-get-started.md#import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider).
3. Skapa en funktion för e-fakturering för organisation. För mer information, se [Skapa en e-faktureringsfunktion under organisationsleverantör](e-invoicing-get-started.md#create-an-electronic-invoicing-feature-under-your-organization-provider).

## <a name="configure-an-email-account-channel"></a>Konfigurera en e-postkontokanal

Konfigurera en e-postkontokanal om du med hjälp av e-faktureringsfunktionen importerar elektroniska leverantörsfakturor från bifogade filer som tas emot via e-post.

1. I RCS, välj den funktion för e-fakturering som du har skapat. Se till att du väljer den version som har status **utkast**.
2. På fliken **Inställningar** i rutnätet, välj en funktionsinställning och välj sedan **Redigera**.
3. Ange kanalens namn på fliken **Datakanal** i fältgruppen **Parametrar**, i fältet **Datakanal**. Kanalnamnet får inte vara längre än tio tecken.
4. I fältet **Serveradress** anger du avsändarens e-postleverantör. Serveradressen för **https://outlook.live.com/** är till exempel **imap-mail.outlook.com**.
5. I fältet **Serverport** anger du den port som används av e-postkontoprovidern. Serverporten för **https://outlook.live.com/** är till exempel **993**.
6. I fältet **Hemlighet för användarnamn** anger du namnet på nyckelvalvhemligheten som innehåller ID för e-postanvändarkontot. Denna hemlighet måste skapas i Azure Key Vault och konfigureras i din tjänstemiljö. 
7. I fältet **Hemlighet för användarlösenord** anger du namnet på nyckelvalvhemligheten som innehåller lösenordet för e-postanvändarkontot.
8. Valfritt – Ange värden i fälten **Från-filter**, **Ämnesfilter** och **Datumfilter**.
9. Ange namnen på de postlådemappar där e-postmeddelandena ska vara:

    - Importerad från: **Huvudmapp**
    - Sparad efter att bearbetningen lyckades: **Arkiv-mappen**
    - Sparas när bearbetningen inte lyckas: **Felmapp** Du behöver inte skapa mapparna i postlådan. Mapparna skapas automatiskt efter den första importen och bearbetningen av e-fakturor. 
   
10. I fältgruppen **Bilagefilter** lägger du till filfiltreringsinformationen. Endast bilagor som uppfyller det definierade filtret bearbetas. Du kan till exempel ställa in "\*.xml" för bilagor med XML-tillägg. Namnet på bilagan används i Dynamics 365 Finance eller Dynamics 365 Supply Chain Management under konfiguration. 
11. På fliken **Tillämplighetsregler** kan du granska och uppdatera kriterierna efter behov. Fältet **Kanal** måste vara samma som den **Datakanal** som angetts tidigare. Mer information finns i [Tillämplighetsregler](e-invoicing-configuration-rcs.md#applicability-rules).
12. Markera **Spara** och stäng sedan sidan.

### <a name="configure-a-microsoft-sharepoint-channel"></a>Konfigurera Microsoft SharePoint-kanal

Konfigurera en Microsoft SharePoint-kanal om funktionen e-fakturering importerar elektroniska leverantörsfakturor från filer i SharePoint-mappar.

1. I RCS, välj den funktion för e-fakturering som du har skapat. Se till att du väljer den **version** som har status **utkast**.
2. På fliken **Inställningar** i rutnätet, välj en funktionsinställning och välj sedan **Redigera**.
3. På fliken **Datakanal** i fältgruppen **Parametrar** väljer du **SharePoint adress** och anger SharePoint URL.
4. Välj **serverport** och ange den port som används av e-postkontoprovidern.
5. Välj **App-Id** och ange namnet på Key Vault-hemligheten som innehåller ID för SharePoint-klient.
6. Välj **Programhemligheten** och ange namnet på Key Vault-hemligheten som innehåller lösenord för SharePoint-klient.
7. Välj **Filfilter**. Granska och uppdatera masken för att filtrera filerna som innehåller den elektroniska leverantörsfakturan som ska importeras.
8. På fliken **Tillämplighetsregler** kan du granska och uppdatera kriterierna om det behövs. Mer information finns i [Tillämplighetsregler](e-invoicing-configuration-rcs.md#applicability-rules).
9. Markera **Spara** och stäng sedan sidan

### <a name="deploy-an-electronic-invoicing-feature"></a>Distribuera e-faktureringsfunktionen

Om du vill distribuera funktionen e-fakturering, se [Distribuera funktionen e-fakturering till tjänstemiljön](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment).

## <a name="set-up-vendor-invoice-import-in-finance-or-supply-chain-management"></a>Konfigurera leverantörsfakturaimport i Finance eller Supply Chain Management
Gör stegen i följande två avsnitt om du vill ställa in olika typer av import av leverantörsfaktura.

### <a name="import-brazilian-nf-e-from-email"></a>Importera brasiliansk NF-e från e-post

1. Logga in i Finance eller Supply Chain Management-miljö och kontrollera att du befinner dig i rätt juridisk person.
2. Gå till **Organisationsadministration** > **Inställningar** > **Parametrar för elektroniskt dokument**.
3. På flik **Funktioner**, se till att **NF-e Federal - Brasiliansk e-faktura** är vald.
4. På fliken **Externa kanaler**, i fältgruppen **Kanaler**, välj **Lägg till**.
5. I fältet **Kanalen**, ange **NFe** (namnet på kanalen som anges i konfigurationen av datakanalen för funktionen e-fakturering i RCS).
6. Ange en beskrivning i fältet **beskrivning**. Välj den juridiska personen i fältet **Företag**.
7. I fältet **Dokumentkontext** väljer du **Skattedokument kontext – Kundfaktura kontextmodell**.
8. I fältgruppen **Importera källor**, välj **Lägg till**.
9. I fältet **Namn**, ange **XmlFile** (namnet för **Bilagefilter** anges i datakanalens konfiguration för funktionen e-fakturering i RCS).
10. I fältet **Beskrivning** ange en beskrivning och i **Dataenhetens namn**, välj **Mottagna NF-e XML-dokument**.
11. I fältet **Modellmappning**, välj **NF-e-postimport-NF-e-postimport (BR)** och välj **Spara**.
12. På fliken **Elektroniskt dokument**, fältet **Elektroniskt dokument**, välj **Lägg till** och fältet **Tabellnamn**, välj **Mottaget NF-e XML-dokument**.
13. I fältet **Dokumentkontext** väljer du **Fråga skattemässigt dokument sammanhang – Kundfaktura kontext**.
14. I fältet **Modellmappning av Elektronisk dokumentmodell**, välj **Fråga kartläggning - Finansiell dokumentmappning**.
15. Välj **svarstyper** och välj sedan **Ny**.
16. I fältet **svarstyp** anger du **Svar**. I fältet **Överföringsstatus** välj **Schemalagt**.
17. I fältet **Modellmappning** välj **Modellmappning från svarsmeddelande - Importformat för svarsmeddelande**.
18. Markera **Spara** och stäng sedan sidan.

### <a name="import-peppol-electronic-vendor-invoices"></a>PEPPOL importerar elektroniska leverantörsfakturor

1. På arbetsytan **Elektronisk rapportering** väljer du panelen **Rapporteringskonfiguration**.
2. Välj **Kontextmodell för kundfaktura** och välj **Skapa konfiguration** > **Härled från namn: kontextmodell för kundfaktura, Microsoft** för att skapa en härledd konfiguration.
3. I versionen **Utkast** väljer du **Designer** och i trädet **Datamodell** välj **Mappa modell till datakälla**.
4. I trädet **Definitioner**, välj **DataChannel** och välj **Designer**.
5. I trädet **Datakällor**, visa containern **$Context\_kanal**. 
6. I fältet **Värde** välj **Redigera** > **Redigera formel** och ange namnet på datakanalen. Detta är namnet kanalen, ange namnet på kanalen som anges i konfigurationen av datakanalen för funktionen e-fakturering i RCS. 
7. Markera **Spara** och stäng sedan sidan.
8. Stäng sidan.
9. Välj den härledda konfigurationen som du just skapat från **kontextmodellen för kundfaktura**, och på snabbfliken **Versioner**, välj **Ändra status** > **Slutförd**.
10. Gå till **Organisationsadministration** > **Inställningar** > **Parametrar för elektroniska dokument** och **Funktioner**, se till att **PEPPOL Globala e-fakturor** är markerad. 
11. På fliken **Externa kanaler**, i fältgruppen **Kanaler**, välj **Lägg till**.
12. I fältet **Kanal**, ange namnet på datakanalen och ange en beskrivning i fältet **Beskrivning**.
13. Välj den juridiska personen i fältet **Företag**. 
14. I fältet **Dokumentkontext** väljer du den nya härledda konfigurationen från **Kontextmodell för kundfaktura**. Mappningsbeskrivningen ska vara **Datakanalkontext**.
15. I fältgruppen **Importera källor**, välj **Lägg till**.
16. I fältet **Namn** anger du **bilagefiltrets namn** och i fältet **Dataenhetens namn** väljer du **Leverantörsfakturahuvud**.
17. I fältet **Modellmappning** väljer du **Import för leverantörsfaktura - Importera leverantörsfaktura**.
18. Klicka på **Spara** och stäng sedan sidan.


## <a name="receive-electronic-invoices"></a>Ta emot e-fakturor

Den e-faktureringstjänsten utför två steg under fakturaimporten från datakanalerna:

1. Får åtkomst till postlådan och läser e-post.
2. Bearbetar e-post. 
    
Om du vill utföra dessa två steg ska klienten anropa tjänsten manuellt för varje steg. Vi rekommenderar dock att du ställer in batchjobb för mottagning av elektroniska dokument.

Så här tar du emot e-fakturor:

1. Gå till **Organisationsadministration** > **Periodisk** > **Elektroniska dokument** > **Ta emot elektroniska dokument**.
2. Markera **OK** och stäng sedan sidan.


## <a name="view-receive-logs-for-electronic-invoices"></a>Visa ta emot loggar för e-fakturor

Om du vill visa loggfilerna för e-fakturor går du till **Organisationadministration** > **Periodisk** > **Elektroniska dokument** > **Elektronisk dokumentkvittologg**.
Om du inte ser fakturor som har bearbetats slutfört tar du bort tabellfiltret.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
