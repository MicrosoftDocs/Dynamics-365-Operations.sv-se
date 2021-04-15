---
title: Importera verifikationer med hjälp av enheten Allmän journal
description: Det här ämnet innehåller tips för import av data till den allmänna journalen med hjälp av enheten Allmän journal.
author: rcarlson
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 94363
ms.assetid: 0b8149b5-32c5-4518-9ebd-09c9fd7f4cfc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9a8046cf59f47799627dc09e2b788ab7bdd727e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749680"
---
# <a name="importing-vouchers-by-using-the-general-journal-entity"></a>Importera verifikationer med hjälp av enheten Allmän journal

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller tips för import av data till den allmänna journalen med hjälp av enheten Allmän journal.

Du kan använda enheten Allmän journal för att importera verifikationer som har motkontotypen **Redovisning**, **Kund**, **Försäljare** eller **Bank**. Verifikationen kan anges som en rad med hjälp av både fältet **Konto** och fältet **Motkonto** eller som en flerradig verifikation där endast fältet **Konto** används (och fältet **Motkonto** är tomt på varje rad). Redovisningsjournalenheten stöder inte varje kontotyp. Det finns i stället andra enheter för scenarier där det krävs olika kombinationer av kontotyper. Om du till exempel vill importera en projekttransaktion använder du projektutgiftsjournalenheten. Varje entitet är utformad för att stödja specifika scenarier. Detta innebär att ytterligare fält kan vara tillgängliga i entiteter för dessa scenarier. Ytterligare fält är emellertid inte tillgängliga i entiteter för olika scenarier.

## <a name="setup"></a>Konfigurera
Innan du genomför en import med hjälp av enheten Allmän journal ska du verifiera följande inställningar:

- **Nummerserieinställningarna för journalbatchnumren** – När du genomför en import med hjälp av enheten Allmän journal använder journalbatchnumret den nummerserie som definierats i Allmänna huvudboksparametrar som standard. Om du har ställt in nummerserien för journalbatchnumret till **Manuell** tillämpas inget standardnummer. Den här inställningen stöds inte.
- **Konfigurationen för den ekonomiska dimensionen** – Varje organisation måste definiera ordningen för ekonomiska dimensioner när enheter används för att importera transaktioner. Ordern har definierats för formatet **Integrering av redovisningsdimensioner** i **Redovisning** &gt; **Kontoplaner** &gt; **Dimensioner** &gt; **Konfiguration av ekonomiska dimensioner för integrering av programvaror** &gt; **Välj dataenheter**. Segmenten i det redovisningskonto som importeras måste ha samma ordning. I annat fall visas ett felmeddelande under importen.

## <a name="general-journal-entity-setup"></a>Ställa in allmän journal
Två inställningar i datahantering påverkar hur standardjournalens batchnummer eller verifikationsnummer används:

- **Uppsättningsbaserad bearbetning** (på dataenheten)
- **Automatiskt skapad** (på fältmappning)

I följande avsnitt beskrivs effekterna av dessa inställningar. De förklarar också hur systemet genererar batchjournaler för journaler och verifikationsnummer.

### <a name="journal-batch-number"></a>Journalbatchnummer

- Inställningen för **Uppsättningsbaserad bearbetning** i enheten Allmän journal påverkar inte hur att journalbatchnummer skapas.
- Om fältet **Journalbatchnummer** är inställt på **Automatiskt skapad** skapas ett nytt journalbatchnummer för varje rad som importeras. Detta beteende rekommenderas inte. Inställningen **Automatiskt skapade** hittas i importprojektet under **Visa karta** i fliken **Mappningsdetaljer**.
- Om fältet **Journalbatchnummer** inte är inställt på **Automatiskt skapad** skapas ett nytt journalbatchnummer enligt följande:

    - Om journalbatchnumret som definieras i den importerade filen matchar en befintlig, ej bokförd daglig journal importeras alla rader som har ett matchande journalbatchnummer till den befintliga journalen. Raderna importeras aldrig in i ett bokfört journalbatchnummer. I stället skapas ett nytt nummer.
    - Om journalbatchnumret som definieras i den importerade filen inte matchar en befintlig, ej bokförd daglig journal grupperas alla rader som har samma journalbatchnummer under en ny journal. Alla rader som till exempel har journalbatchnummer 1 importeras till en ny journal och alla rader som har journalbatchnummer 2 importeras till en andra ny journal. Journalbatchnumret skapas med hjälp av den nummerserie som definierats i Allmänna huvudboksparametrar.

### <a name="voucher-number"></a>Verifikationsnummer

- Om du använder inställningen **Uppsättningsbaserad bearbetning** för enheten Allmän journal måste verifikationsnumret anges i den importerade filen. Varje transaktion i den allmänna journalen tilldelas det verifikationsnummer som tillhandahålls i den importerade filen även om verifikationen inte är balanserad. Observera följande punkter om du vill använda uppsättningsbaserad bearbetning men även vill använda det nummerserie som har definierats för verifikationsnummer.

    - Om du vill aktivera den här funktionen på journalnamnet som används för importer, ställ in **Nummerallokering vid bokföring** på **Ja**.
    - Ett verifikationsnummer måste fortfarande definieras i den importerade filen. Detta nummer är dock temporärt och skrivs över av verifikationsnumret när journalen bokförs. Du måste kontrollera att raderna i journalen är korrekt grupperade efter temporära verifikationsnummer. Till exempel under bokföring hittas tre rader som har ett tillfälligt verifikationsnummer 1. Det tillfälliga verifikationsnumret för alla tre rader skrivs över av nästa nummer i nummerserien. Om dessa tre rader inte är balanserade poster bokförs inte verifikationen. Om det dessutom finns rader som har det temporära verifikationsnumret 2 skrivs det här numret över med nästa verifikationsnummer i serien och så vidare.

- Om du inte använder inställningen **Uppsättningsbaserad bearbetning** behöver inget verifikationsnummer anges i den importerade filen. Verifikationsnumren skapas under importen baserat på inställningen för journalnamn (**endast en verifikation**, **ihop med saldo** och så vidare). Om journalnamnet exempelvis definieras som **Ihop med saldo** får den första raden ett nytt standardverifikationsnummer. Systemet utvärderar sedan raden för att fastställa om debet överensstämmer med kredit. Om det finns ett motkonto på raden får nästa rad som importeras ett nytt verifikationsnummer. Om det inte finns något motkonto utvärderar systemet om debet är lika med kredit allt eftersom varje ny rad importeras.
- Om fältet **Verifikationsnummer** är inställt på **Automatiskt skapad** misslyckas importen. Inställningen **Automatiskt skapad** för fältet **Verifikationsnummer** stöds inte.

Enheten Allmän journal använder uppsättningsbaserad bearbetning. När du utvärderar affärskraven för din organisation kan du ändra inställningen **Uppsättningsbaserad bearbetning** genom att klicka på **Datatabeller** i arbetsytan **Datahantering**. Uppsättningsbaserad bearbetning används för att påskynda importprocessen. Om du inte använder uppsättningsbaserad bearbetning går importen av enheten Allmän journal långsammare.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]