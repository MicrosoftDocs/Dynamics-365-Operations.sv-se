---
title: "Regelverk för att importera verifikationer med hjälp av enheten Allmän journal"
description: "Det här ämnet innehåller tips för import av data till den allmänna journalen med hjälp av enheten Allmän journal."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 94363
ms.assetid: 0b8149b5-32c5-4518-9ebd-09c9fd7f4cfc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a45a75d23c77af86b55866f99a97343a210ec777
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="best-practices-for-importing-vouchers-using-the-general-journal-entity"></a>Regelverk för att importera verifikationer med hjälp av enheten Allmän journal

[!include[banner](../includes/banner.md)]


Det här ämnet innehåller tips för import av data till den allmänna journalen med hjälp av enheten Allmän journal.  

Du kan använda enheten Allmän journal för att importera verifikationer som har motkontotypen **Redovisning, Kund, Försäljare, eller Bank**. Verifikationen kan anges som en rad med hjälp av både fältet **Konto** och fältet **Motkonto** eller som en flerradig verifikation där endast fältet **Konto** används (och fältet **Motkonto** är tomt på varje rad). Redovisningsjournalenheten stöder inte varje kontotyp. Det finns i stället andra enheter för scenarier där det krävs olika kombinationer av kontotyper. Om du till exempel vill importera en projekttransaktion använder du projektutgiftsjournalenheten. Varje enhet har utformats för speciella scenarier vilket innebär att ytterligare fält kan vara tillgängliga för dessa scenarier men inte enheter för ett annat scenario.

## <a name="setup"></a>Inställningar
Innan du genomför en import med hjälp av enheten Allmän journal ska du verifiera följande inställningar:

-   **Nummerserieinställningarna för journalbatchnumren** – När du genomför en import med hjälp av enheten Allmän journal använder journalbatchnumret den nummerserie som definierats i Allmänna huvudboksparametrar som standard. Om du har ställt in nummerserien för journalbatchnumret till **Manuell** tillämpas inget standardnummer. Den här inställningen stöds inte.
-   **Konfigurationen för den ekonomiska dimensionen** – Varje organisation måste definiera ordningen för ekonomiska dimensioner när enheter används för att importera transaktioner. Ordern har definierats för formatet **Integrering av redovisningsdimensioner** i **Redovisning** &gt; **Kontoplaner** &gt; **Dimensioner** &gt; **Konfiguration av ekonomiska dimensioner för integrering av programvaror** &gt; **Välj dataenheter**. Segmenten i det redovisningskonto som importeras måste ha samma ordning. I annat fall visas ett felmeddelande under importen.

## <a name="general-journal-entity-setup"></a>Ställa in allmän journal
Två inställningar i datahantering påverkar hur standardjournalens batchnummer eller verifikationsnummer används:

-   **Uppsättningsbaserad bearbetning** (på dataenheten)
-   **Automatiskt genererad** (på fältmappning)

Följande avsnitt innehåller en beskrivning av effekten av dessa inställningar och hur journalbatchnummer och verifikationsnummer genereras.

### <a name="journal-batch-number"></a>Journalbatchnummer

-   Inställningen för **Uppsättningsbaserad bearbetning** i enheten Allmän journal påverkar inte hur att journalbatchnummer genereras.
-   Om fältet **Journalbatchnummer** är inställt på **Automatiskt genererad** skapas ett nytt journalbatchnummer för varje rad som importeras. Detta beteende rekommenderas inte. Inställningen **Automatiskt genererade** hittas i importprojektet under **Visa karta** i fliken **Mappningsdetaljer**.
-   Om fältet **Journalbatchnummer** inte är inställt på **Automatiskt genererad** skapas ett nytt journalbatchnummer enligt följande:
    -   Om journalbatchnumret som definieras i den importerade filen matchar en befintlig, ej bokförd daglig journal importeras alla rader som har ett matchande journalbatchnummer till den befintliga journalen. Raderna importeras aldrig in i ett bokfört journalbatchnummer. I stället skapas ett nytt nummer.
    -   Om journalbatchnumret som definieras i den importerade filen inte matchar en befintlig, ej bokförd daglig journal grupperas alla rader som har samma journalbatchnummer under en ny journal. Alla rader som till exempel har journalbatchnummer 1 importeras till en ny journal och alla rader som har journalbatchnummer 2 importeras till en andra ny journal. Journalbatchnumret skapas med hjälp av den nummerserie som definierats i Allmänna huvudboksparametrar.

### <a name="voucher-number"></a>Verifikationsnummer

-   Om du använder inställningen **Uppsättningsbaserad bearbetning** för enheten Allmän journal måste verifikationsnumret anges i den importerade filen. Varje transaktion i den allmänna journalen tilldelas det verifikationsnummer som tillhandahålls i den importerade filen även om verifikationen inte är balanserad. Om du vill använda uppsättningsbaserad bearbetning men även vill använda det nummerserie som har definierats för verifikationsnummer finns det en snabbkorrigering för i februariutgåvan 2016. Snabbkorrigeringsnumret är 3170316 och kan hämtas från Lifestyle services (LCS). Mer information hittar du i [Hämta snabbkorrigeringar från Lifestyle Services](..\migration-upgrade\download-hotfix-lcs.md).
    -   Om du vill aktivera den här funktionen på journalnamnet som används för importer, ställ in **Nummerallokering vid bokföring** på **Ja**.
    -   Ett verifikationsnummer måste fortfarande definieras i den importerade filen. Detta nummer är dock temporärt och skrivs över av verifikationsnumret när journalen bokförs. Du måste kontrollera att raderna i journalen är korrekt grupperade efter temporära verifikationsnummer. Till exempel under bokföring hittas tre rader som har ett tillfälligt verifikationsnummer 1. Det tillfälliga verifikationsnumret för alla tre rader skrivs över av nästa nummer i nummerserien. Om dessa tre rader inte är balanserade poster bokförs inte verifikationen. Om det dessutom finns rader som har det temporära verifikationsnumret 2 skrivs det här numret över med nästa verifikationsnummer i nummerserien och så vidare.

<!-- -->

-   Om du inte använder inställningen **Uppsättningsbaserad bearbetning** behöver inget verifikationsnummer anges i den importerade filen. Verifikationsnumren skapas under importen baserat på inställningen för journalnamn (**endast en verifikation**, **ihop med saldo** och så vidare). Om journalnamnet exempelvis definieras som **Ihop med saldo** får den första raden ett nytt standardverifikationsnummer. Systemet utvärderar sedan raden för att fastställa om debet överensstämmer med kredit. Om det finns ett motkonto på raden får nästa rad som importeras ett nytt verifikationsnummer. Om det inte finns något motkonto utvärderar systemet om debet är lika med kredit allt eftersom varje ny rad importeras.
-   Om fältet **Verifikationsnummer** är inställt på **Automatiskt genererad** misslyckas importen. Inställningen **Automatiskt genererad** för fältet **Verifikationsnummer** stöds inte.

Enheten Allmän journal använder uppsättningsbaserad bearbetning. När du utvärderar affärskraven för din organisation kan du ändra inställningen **Uppsättningsbaserad bearbetning** genom att klicka på **Datatabeller** i arbetsytan **Datahantering**. Uppsättningsbaserad bearbetning används för att påskynda importprocessen. Om du inte använder uppsättningsbaserad bearbetning går importen av enheten Allmän journal långsammare.




