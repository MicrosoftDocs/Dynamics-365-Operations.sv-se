---
title: "Avskrivning förteckning över uppgradering: översikt"
description: "I tidigare versioner har två värdering begrepp för anläggningstillgångar - värdemodeller och avskrivningsregler. I Microsoft Dynamics 365 for Operations, version 1611, har värdemodellfunktionen och funktionen för avskrivningsregel slagits ihop till ett enda begrepp som kallas för &quot;bok&quot;. Detta avsnitt listar några saker att beakta i samband med uppgraderingen."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer
ms.search.scope: Operations, Core
ms.custom: 221624
ms.assetid: cf434099-36f9-4b0f-a7c8-bed091e34f39
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: bec019d218d80ba059d5a1c232072f46b1ae3ee2
ms.openlocfilehash: d29cb7bc5acc29be93332b4211adebc4486a7a25
ms.lasthandoff: 03/31/2017


---

# <a name="depreciation-book-upgrade-overview"></a>Avskrivning förteckning över uppgradering: översikt

I tidigare versioner har två värdering begrepp för anläggningstillgångar - värdemodeller och avskrivningsregler. I Microsoft Dynamics 365 for Operations, version 1611, har värdemodellfunktionen och funktionen för avskrivningsregel slagits ihop till ett enda begrepp som kallas för "bok". Detta avsnitt listar några saker att beakta i samband med uppgraderingen. 

Uppgraderingsprocessen flyttar din befintliga inställning och alla befintliga transaktioner till den nya bokstrukturen. Värdemodeller kommer att kvarstå som de är, som en bok som bokförs till huvudboken. Avskrivningsregler flyttas till en bok som har alternativet **Post to general ledger** inställt på **No**. Journalnamn för avskrivningsregler som ska flyttas till en redovisningsjournalnamn med bokföringsskiktet som **ingen**. Transaktioner för avskrivningsregel ska flyttas till transaktioner för anläggningstillgångar. 

Innan du kör datauppgraderingen bör du förstå de två tillgängliga alternativen för uppgradering av journalraderna i avskrivningsregler till transaktionsverifikationer, samt den nummerserie som kommer att användas för verifikationsserien. 

Alternativ 1:  **System-defined number sequence** - Detta är standardalternativet för att optimera uppgraderingsprestandan. Uppgraderingen använder inte nummerserieramverket, utan allokerar istället verifikationer med en uppsättningsbaserad inställning. Efter uppgraderingen måste den nya nummerserien skapas med den **nästa inställt antal** utifrån uppgraderade transaktionerna på rätt sätt. Som standard blir den nummerserie som används i FADBUpgr\#\#\#\#\#\#\#\#\# format. Det finns några parametrar för att justera format när du använder den här metoden:

-   **Nummerseriekod** – den kod som identifierar nummerserien. Den här nummerseriekoden kan inte existera eftersom den skapas av uppgraderingen.
    -   Konstantnamn: **NumberSequenceDefaultCode**
    -   Standardvärde: "FADBUpgr"
-   **Prefix** – Konstantsträngvärdet som ska användas som ett prefix för verifikationsnumren.
    -   Konstantnamn: **NumberSequenceDefaultParameterPrefix**
    -   Standardvärde: "FADBUpgr"
-   **Alfanumerisk längd** – Längden på det alfanumeriska segmentet i nummerserien.
    -   Fasta namn: ** NumberSequenceDefaultParameterAlpanumericLength **
    -   Standardvärde: 9
-   **Start number** - Det första nummer som ska användas i nummerserien.
    -   Fasta namn: ** NumberSequenceDefaultParameterStartNumber **
    -   Standardvärde: 1

Alternativ 2: **befintliga användardefinierade nummerserien** -inställningen kan du definiera nummerserien som ska användas för att uppgradera. Kan du använda det här alternativet om du behöver avancerade nummerseriekonfiguration. Om du vill använda en nummerserie måste du ändra uppgradering klassen ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans med följande information:

-   **Number sequence code** – Nummerseriens kod.
    -   Fasta namn: ** NumberSequenceExistingCode **
    -   Förvalt värde: Ingen standardinställning, detta måste uppdateras till nummerseriekoden.
-   **Shared number sequence** – Ett booleskt värde som identifierar omfånget på nummerserien. Använd ”true” för delade nummerserier för alla företag,” och ”false" för ett företagsspecifikt omfång. När du använder "false" måste nummerserien med det angivna namnet finnas i alla företag som innehåller transaktioner för avskrivningsregler. Delad nummerserier finns i alla partitioner som innehåller transaktioner för avskrivningsregler.
    -   Fasta namn: ** NumberSequenceExistingIsShared **
    -   Standardvärde: true

Parametrarna finns i början av ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans class. 

*Anger en bättre metod för allokering av verifikationer*<ph id="t1"></ph>*/ / SANT om du vill använda en befintlig nummerseriekod*<ph id="t2"></ph>*/ / false om du tänker använda systemdefinierade nummerserie (standard)* y boolean NumberSequenceUseExistingCode = FALSKT.  

*Om du använder metoden systemdefinierade nummer sekvens, ange parametrar för nummerserien. *<ph id="t3"></ph>*/ / En ny nummerserie ska skapas enligt följande parametrar.* Const str NumberSequenceDefaultCode = FADBUpgr; Const str NumberSequenceDefaultParameterPrefix = FADBUpgr; int Const NumberSequenceDefaultParameterAlpanumericLength = 9. int Const NumberSequenceDefaultParameterStartNumber = 1;   

*Om du använder metoden befintliga serie tal, ange befintliga nummerseriekoden. *<ph id="t4"></ph>*/ / Allokering av verifikation fördelas rad för rad för befintliga nummerserierna.* Const str NumberSequenceExistingCode = ''; */ / Ange intervallet för den befintliga nummerseriekoden*<ph id="t5"></ph>*/ / SANT om den angivna nummerserien delas*<ph id="t6"></ph>*/ / falskt om den angivna nummerserien är per företag*<ph id="t7"></ph>*/ / systemdefinierade standardnummerserien används om det inte finns en nummerseriekod med definitionsområdet.* const boolean NumberSequenceExistingIsShared = true; 

Skapa om projektet som innehåller klassen efter det att konstanterna har ändrats. 

När du använder den systemgenererade nummer sekvens metoden (alternativ 1) kan använder uppgraderingen uppsättning baserat processing tilldelas verifikationsnummer som angetts i parametrarna för uppgraderingsskript. Dessutom skapas en ny nummerserie med angivna parametrar efter allokeringen. 

När du använder den användardefinierade, befintliga nummerserieinställningen (alternativ 2) kontrollera datauppgraderingen om nummerserien med det angivna omfånget finns i databasen för respektive partition och företag med transaktioner i avskrivningsregeln. Om det finns använder uppgraderingen rad för rad bearbetning enligt nummerserien med hjälp av nummersekvensramverk verifikationsnumren tilldelas. Om nummerserien inte finns med i definitionsområdet uppgraderingen används standard systemdefinierade nummer sekvens metoden verifikationsnumren tilldelas och skapar en ny nummerserie med angivna standardparametrar efter allokeringen.

Oavsett metod kommer datauppgraderingsskriptet också att använda nummerserien för fältet **Voucher series** på de nya redovisningsjournalnamnen som skapas för de tidigare journalnamnen i avskrivningsregeln.


