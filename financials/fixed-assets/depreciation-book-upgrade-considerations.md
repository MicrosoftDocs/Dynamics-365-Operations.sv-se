---
title: "Uppgraderingsöversikt för avskrivningsregler"
description: "I tidigare versioner fanns två värderingsbegrepp för anläggningstillgångar: värdemodeller och avskrivningsregler. I Microsoft Dynamics 365 for Operations, version 1611, har värdemodellfunktionen och funktionen för avskrivningsregel slagits ihop till ett enda begrepp som kallas för &quot;bok&quot;. Detta avsnitt listar några saker att beakta i samband med uppgraderingen."
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

# <a name="depreciation-book-upgrade-overview"></a>Uppgraderingsöversikt för avskrivningsregler

[!include[banner](../includes/banner.md)]


I tidigare versioner fanns två värderingsbegrepp för anläggningstillgångar: värdemodeller och avskrivningsregler. I Microsoft Dynamics 365 for Operations, version 1611, har värdemodellfunktionen och funktionen för avskrivningsregel slagits ihop till ett enda begrepp som kallas för "bok". Detta avsnitt listar några saker att beakta i samband med uppgraderingen. 

Uppgraderingsprocessen flyttar din befintliga inställning och alla befintliga transaktioner till den nya bokstrukturen. Värdemodeller kommer att kvarstå som de är, som en bok som bokförs till huvudboken. Avskrivningsregler flyttas till en bok som har alternativet **Post to general ledger** inställt på **No**. Journalnamn för avskrivningsregel flyttas till ett journalnamn för huvudbok som har bokföringsskiktet inställt på **Ingen**. Transaktioner för avskrivningsregler flyttas till transaktioner för anläggningstillgångar. 

Innan du kör datauppgraderingen bör du förstå de två tillgängliga alternativen för uppgradering av journalraderna i avskrivningsregler till transaktionsverifikationer, samt den nummerserie som kommer att användas för verifikationsserien. 

Alternativ 1:  **System-defined number sequence** - Detta är standardalternativet för att optimera uppgraderingsprestandan. Uppgraderingen använder inte nummerserieramverket, utan allokerar istället verifikationer med en uppsättningsbaserad inställning. Efter uppgraderingen skapa den nya nummerserien **Nästa inställda nummer** lämpligt baserad på uppgraderade transaktioner. Som standard kommer använd nummerserie att vara i formatet FADBUpgr\#\#\#\#\#\#\#\#\#. Det finns några parametrar där du kan justera formatet när du använder den här metoden:

-   **Nummerseriekod** – Den kod som identifierar nummerserien. Denna nummerseriekod kan inte existera eftersom den skapas av uppgraderingen.
    -   Konstantnamn: **NumberSequenceDefaultCode**
    -   Standardvärde: "FADBUpgr"
-   **Prefix** – Konstantsträngvärdet som ska användas som ett prefix för verifikationsnumren.
    -   Konstantnamn: **NumberSequenceDefaultParameterPrefix**
    -   Standardvärde: "FADBUpgr"
-   **Alfanumerisk längd** – Längden på det alfanumeriska segmentet i nummerserien.
    -   Konstantnamn: **NumberSequenceDefaultParameterAlpanumericLength **
    -   Standardvärde: 9
-   **Start number** - Det första nummer som ska användas i nummerserien.
    -   Konstantnamn: **NumberSequenceDefaultParameterStartNumber  **
    -   Standardvärde: 1

Alternativ 2: **Befintlig användardefinierad nummerserie** - Detta alternativ låter dig definiera den nummerserie som ska användas för uppgraderingen. Överväg att använda detta alternativ om du behöver avancerad konfiguration av nummerserie. Om du vill använda en nummerserie måste du ändra uppgraderingsklassen ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans med följande information:

-   **Number sequence code** – Nummerseriens kod.
    -   Konstantnamn: **NumberSequenceExistingCode **
    -   Förvalt värde: Ingen standardinställning, detta måste uppdateras till nummerseriekoden.
-   **Shared number sequence** – Ett booleskt värde som identifierar omfånget på nummerserien. Använd ”true” för delade nummerserier för alla företag,” och ”false" för ett företagsspecifikt omfång. När du använder "false" måste nummerserien med det angivna namnet finnas i samtliga företag som innehåller transaktioner för avskrivningsregler. Delade nummerserier finns i alla partitioner som innehåller transaktioner för avskrivningsregler.
    -   Konstantnamn: **NumberSequenceExistingIsShared **
    -   Standardvärde: true

Parametrarna finns i början av klassen ReleaseUpdateDB70\_FixedAssetJournalDepBookRemovalDepBookJournalTrans class. 

*// Ange en bättre metod för allokering av verifikationer* 
*// true,om du vill använda en befintlig nummerseriekod* 
*// false, om du tänker använda systemdefinierad nummerserie (standard)* const boolean NumberSequenceUseExistingCode = false;  

*// Om du använder metoden systemdefinierad nummersekvens, ange parametrarna för nummerserien*
*// En ny nummerserie skapas med följande parametrar.* const str NumberSequenceDefaultCode = 'FADBUpgr'; const str NumberSequenceDefaultParameterPrefix = 'FADBUpgr'; const int NumberSequenceDefaultParameterAlpanumericLength = 9; const int NumberSequenceDefaultParameterStartNumber = 1;   

*// Om du använder metoden med befintliga nummerserier, ange befintlig nummerseriekod.* 
*// Allokering av verifikation sker rad för rad för befintliga nummerserier.* const str NumberSequenceExistingCode = ''; *// Ange intervallet för den befintliga nummerseriekoden* 
*// true, om den angivna nummerserien delas* 
*// false, om den angivna nummerserien är per företag* 
*// Den systemdefinierade standardnummerserien används om det inte finns någon nummerseriekod med angivet intervall.* const boolean NumberSequenceExistingIsShared = true; 

Skapa om projektet som innehåller klassen efter det att konstanterna har ändrats. 

När du använder metoden med systemgenererad nummersekvens (alternativ 1) använder uppgraderingen uppsättningsbaserad bearbetning för att fördela verifikationsnummer enligt de parametrar som angetts för uppgraderingsparametrarna. Dessutom skapas en ny nummerserie med angivna parametrar efter allokeringen. 

När du använder den användardefinierade, befintliga nummerserieinställningen (alternativ 2) kontrollera datauppgraderingen om nummerserien med det angivna omfånget finns i databasen för respektive partition och företag med transaktioner i avskrivningsregeln. Om den finns använder uppgraderingen bearbetning rad för rad för att allokera verifikationsnumren enligt nummerserien med hjälp av nummersekvensramverket. Om nummerserien inte finns med i angivet definitionsområde, kommer uppgraderingen att använda metoden med förvald, systemdefinierad nummersekvens för att allokera verifikationsnumren, samt skapa en ny nummersekvens med angivna standardparametrar efter allokeringen.

Oavsett metod kommer datauppgraderingsskriptet också att använda nummerserien för fältet **Voucher series** på de nya redovisningsjournalnamnen som skapas för de tidigare journalnamnen i avskrivningsregeln.




