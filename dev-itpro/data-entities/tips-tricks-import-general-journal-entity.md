---
title: "Tips för att importera verifikationer med entiteten redovisningsjournal"
description: "I det här avsnittet innehåller tips för att importera data till den allmänna journalen genom att använda allmänna journalen entitet."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 94363
ms.assetid: 0b8149b5-32c5-4518-9ebd-09c9fd7f4cfc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 81a52acd1d9baa12fcfe9d848441901894fa5682
ms.lasthandoff: 03/31/2017


---

# <a name="best-practices-for-importing-vouchers-using-the-general-journal-entity"></a>Tips för att importera verifikationer med entiteten redovisningsjournal

I det här avsnittet innehåller tips för att importera data till den allmänna journalen genom att använda allmänna journalen entitet.  

Redovisningsjournal enheten gör för att importera verifikationer som konto eller motkonto kontotypen har **redovisning, kund, leverantör eller Bank**. Verifikationen kan anges som en rad med båda **konto** fält och **motkonto** eller som en flerradig verifikation där endast den **konto** används (och **motkonto** är tomt på varje rad). Redovisningsjournal enheten stöder inte varje kontotyp. Det finns i stället andra enheter för scenarier där det krävs olika kombinationer av kontotyper. Till exempel om du vill importera en projekttransaktion använda entiteten journalen projekt utgift. Varje entitet har utformats för speciella scenarier vilket innebär ytterligare fält som kan finnas i enheter för scenarier men inte personer som ett annat scenario.

## <a name="setup"></a>Inställningar
Verifiera följande inställningar innan du importerar med hjälp av redovisningsjournalen enheten:

-   **Nummerserieinställningarna för journalnumret batch** - standard när du importerar med hjälp av entiteten redovisningsjournal i journalen batch som använder den nummerserie som definierats i formuläret Allmänna redovisningsparametrar. Om du har ställt in nummerserien för journalbatchnumret till **Manuell** tillämpas inget standardnummer. Den här inställningen stöds inte.
-   **Konfigurationsnyckel för ekonomisk dimension** -alla organisationer måste definiera fältordningen för ekonomiska dimensioner när personer som används för att importera transaktioner. Ordern har definierats för den **redovisning dimensioner integration** format, vid **redovisning**&gt;**kontoplanen**&gt;**dimensioner**&gt;**ekonomiska dimensionen konfiguration för att integrera program**&gt;**Välj datatabeller**. Segmenten i det redovisningskonto som importeras måste ha samma ordning. I annat fall visas ett felmeddelande under importen.

## <a name="general-journal-entity-setup"></a>Ställa in allmän journal
Två inställningar i datahantering påverkar hur standard Journalbatchnummer eller verifikationsnummer används:

-   **Ställ in baserat processing** (på enheten data)
-   **Automatiskt genererad** (på fältmappning)

Följande avsnitt innehåller en beskrivning av effekten av dessa inställningar och hur journalbatchnummer och verifikationsnummer genereras.

### <a name="journal-batch-number"></a>Journalbatchnummer

-   Inställningen för **Uppsättningsbaserad bearbetning** i enheten Allmän journal påverkar inte hur att journalbatchnummer genereras.
-   Om fältet **Journalbatchnummer** är inställt på **Automatiskt genererad** skapas ett nytt journalbatchnummer för varje rad som importeras. Detta beteende rekommenderas inte. Inställningen **Automatiskt genererade** hittas i importprojektet under **Visa karta** i fliken **Mappningsdetaljer**.
-   Om fältet **Journalbatchnummer** inte är inställt på **Automatiskt genererad** skapas ett nytt journalbatchnummer enligt följande:
    -   Om Journalbatchnummer som definieras i den importerade filen matchar en befintlig, ej bokförda dagboksjournalen i Microsoft Dynamics 365 för operationer visas importeras alla rader som har ett matchande Journalbatchnummer till de befintliga journalerna. Raderna importeras aldrig in i ett bokfört journalbatchnummer. I stället skapas ett nytt nummer.
    -   Om Journalbatchnummer som definieras i den importerade filen inte stämmer överens med en befintlig, ej bokförda dagboksjournalen i Dynamics 365 för operationer, grupperas alla rader som har samma Journalbatchnummer under en ny journal. Alla rader som till exempel har journalbatchnummer 1 importeras till en ny journal och alla rader som har journalbatchnummer 2 importeras till en andra ny journal. Journalbatchnumret skapas med hjälp av den nummerserie som definierats i Allmänna huvudboksparametrar.

### <a name="voucher-number"></a>Verifikationsnummer

-   Om du använder inställningen **Uppsättningsbaserad bearbetning** för enheten Allmän journal måste verifikationsnumret anges i den importerade filen. Varje transaktion i den allmänna journalen tilldelas det verifikationsnummer som tillhandahålls i den importerade filen även om verifikationen inte är balanserad. Om du vill använda uppsättningen baserad bearbetning, men du vill använda den nummerserie som har definierats för verifikationsnummer i Dynamics 365 för operationer, en snabbkorrigering har angetts för februari 2016. Snabbkorrigeringsnumret är 3170316 och kan hämtas från Lifestyle services (LCS). Mer information hittar du i [Hämta snabbkorrigeringar från Lifestyle Services](..\migration-upgrade\download-hotfix-lcs.md).
    -   Aktivera den här funktionen på det journalnamn som används vid import i Dynamics 365 för åtgärder och ange **numrera allokering vid bokföringstillfället** till **Ja**.
    -   Ett verifikationsnummer måste fortfarande definieras i den importerade filen. Numret är tillfälliga och skrivs över av Dynamics 365 för operationer verifikationsnummer när journalen bokförs. Du måste kontrollera att raderna i journalen är korrekt grupperade efter temporära verifikationsnummer. Till exempel registrerar finns tre rader som har ett tillfälligt verifikationsnummer 1. Tillfälligt verifikationsnummer för alla tre rader skrivs över av nästa nummer i nummerserien. Om dessa tre rader inte är balanserade poster bokförs inte verifikationen. Om det dessutom finns rader som har det temporära verifikationsnumret 2 skrivs det här numret över med nästa verifikationsnummer i nummerserien och så vidare.

<!-- -->

-   Om du inte använder den **ange baserat processing** kan du inte behöver ange ett verifikationsnummer i den importerade filen. Verifikationsnumren skapas under importen baserat på inställningen för journalnamn (**endast en verifikation**, **ihop med saldo**och så vidare). Om journalnamnet exempelvis definieras som **Ihop med saldo** får den första raden ett nytt standardverifikationsnummer. Systemet utvärderar sedan raden för att fastställa om debet överensstämmer med kredit. Om det finns ett motkonto på raden får nästa rad som importeras ett nytt verifikationsnummer. Om det inte finns något motkonto utvärderar systemet om debet är lika med kredit allt eftersom varje ny rad importeras.
-   Om fältet **Verifikationsnummer** är inställt på **Automatiskt genererad** misslyckas importen. Inställningen **Automatiskt genererad** för fältet **Verifikationsnummer** stöds inte.

Enheten Allmän journal använder uppsättningsbaserad bearbetning. När du utvärderar affärskraven för din organisation kan du ändra inställningen **Uppsättningsbaserad bearbetning** genom att klicka på **Datatabeller** i arbetsytan **Datahantering**. Uppsättningsbaserad bearbetning används för att påskynda importprocessen. Om du inte använder uppsättningsbaserad bearbetning går importen av enheten Allmän journal långsammare.


