---
title: "Räkenskapsintegration för butikskanal"
description: "I det här avsnittet finns en översikt över räkenskapsintegration för Retail POS."
author: josaw
manager: annbe
ms.date: 11/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2018-11-1
ms.dyn365.ops.version: 8.1.1
ms.translationtype: HT
ms.sourcegitcommit: 0450326dce0ba6be99aede4ebc871dc58c8039ab
ms.openlocfilehash: c852d095505abecbd44d29e9e7b53875e9069def
ms.contentlocale: sv-se
ms.lasthandoff: 11/01/2018

---
# <a name="fiscal-integration-for-retail-channel"></a>Räkenskapsintegration för butikskanal

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en översikt över funktioner för räkenskapsintegration i Microsoft Dynamics 365 for Retail. Funktionen för räkenskapsintegration är ett ramverk som är utformat för att stödja lokala skatteregler som är avsedda att förebygga bedrägeri inom detaljhandel. Typiska scenarier som kan omfatta räkenskapsintegration är:

- Skriva ut kvitto och ge det till kunden.
- Skydda inlämnande av uppgifter som rör försäljning och returer som gjorts i en kassa till en extern tjänst som tillhandahålls av myndigheten.
- Använda dataskydd med en digital signatur som godkänts av myndigheten.

Det här avsnittet ger riktlinjer för att skapa räkenskapsintegration så att användarna kan utföra följande uppgifter. 

- Konfigurera räkenskapskopplingar som är kvittoskrivarenheter eller tjänster som används för räkenskapsregistrering såsom spara, digitala signaturer och skyddad överföring av räkenskapsdata.
- Konfigurera dokumentleverantören, som definierar en för utmatningsmetod och en algoritm för generering av skattedokument.
- Konfigurera räkenskapsregistrering som definierar en följd av steg och en grupp med kontakter som används i varje steg.
- Tilldela räkenskapsregistrering till funktionsprofiler för kassa.
- Tilldela tekniska profiler för koppling, antingen till maskinvaruprofiler (för lokala räkenskapskopplingar) eller till funktionsprofiler för kassa (för andra typer av räkenskapskopplingar).

## <a name="fiscal-integration-execution-flow"></a>Räkenskapsintegration körningsflöde
I följande scenario visar vanligt körningsflöde för räkenskapsintegration.

1. Initialisering av räkenskapsregistreringen.
  
   Efter att ha utfört vissa åtgärder där räkenskapsregister krävs, till exempel när en detaljhandelstransaktion har slutförts, är räkenskapsregistreringen associerad med den nuvarande funktionalitetsprofil för kassa.

1. Sök efter en räkenskapskoppling.
   
   För varje räkenskapsregistreringssteg i räkenskapsregistreringen matchar systemet listan över räkenskapskopplingar. Dessa kopplingar har en funktionell profil som ingår i den angivna kopplingsgruppen med en lista över de kopplingar som har en teknisk profil associerad till den aktuella maskinvaruprofilen (för en typ av koppling som endast motsvarar **lokala**) eller med den aktuella funktionsprofilen för kassa (för andra typer av kopplingar).
   
1. Utför räkenskapsintegrationen.

   Systemet utför alla nödvändiga åtgärder som definieras av en uppsättning kopplade till den hittade kopplingen. Detta görs i enlighet med inställningarna för funktionella profilen och tekniska profilen som hittades i det föregående steget för den här kopplingen.

## <a name="setup-needed-before-using-fiscal-integration"></a>Inställningar behövs innan du använder räkenskapsintegration
Du bör definiera följande inställningar innan du kan använda funktionen räkenskapsintegrering:

- Definiera en nummerserie på sidan **Butiksparametrar** för funktionell profilnummer för räkenskap.
  
- Definiera nummersekvens på sidan **Delade butiksparametrar** för följande referenser:
  
  - Nummer för teknisk profil för räkenskaper
  - Gruppnummer för räkenskapskoppling
  - Nummer för registreringsprocess

- Skapa en **räkenskapskoppling** i **Retail > kanalinställning > räkenskapsintegration > räkenskapskopplingar** för varje enhet eller tjänst som du tänker använda för räkenskapsintegration.

-  Skapa en **skattedokumentleverantör** i **Retail > kanalinställning > räkenskapsintegration > leverantörer av skattedokument** för alla räkenskapskopplingar. Datamappning betraktas som en del av skattedokumentleverantören. Om du vill ställa in olika datamappningar för samma typ av koppling (till exempel delstatsspecifika regler) bör du skapa olika leverantörer för skattedokument.

- Skapa en **Funktionsprofil för koppling** i **Retail > kanalinställning > räkenskapsintegration > Funktionsprofil för koppling** för varje leverantör av skattedokument.
  - Välj namnet på en koppling.
  - Välj en dokumentleverantör.
  - Ange momsinställningar på fliken **tjänstinställning**.
  - Ange momskodmappning och betalningsmedeltypmappning på fliken **Datamappning**.

  #### <a name="examples"></a>Exempel 

  |  | Format | Exempel | 
  |--------|--------|--------|
  | Inställning av momssatser | värde: VATrate | 1 : 2000, 2 : 1800 |
  | Mappning av momskoder | VATcode : värde | vat20 : 1, vat18 : 2 |
  | Mappning av betalningsmedelstyper | TenderTyp: värde | Kontant: 1 kort: 2 |

- Skapa **Grupper för räkenskapskoppling** i **Retail > kanalinställning > räkenskapsintegration > grupp för räkenskapskoppling**. En kopplingsgrupp som är en delmängd av funktionella profiler länkas till räkenskapskopplingar som utför identiska funktioner som används i samma fas inom en räkenskapsregistrering.

   - Lägg till funktionella profiler till kopplingsgruppen. Klicka på **Lägg till** på sidan **funktionella profiler** och välj ett profilnummer.
   - Om du vill skjuta upp förbrukningen av funktionella profilen, ange **inaktivera** till **Ja**. 
   
     Denna ändring påverkar endast aktuella kopplingsgruppen. Du kan fortsätta att använda samma funktionella profil i andra kopplingsgrupper.

     >[!NOTE]
     > Inom en kopplingsgrupp kan varje räkenskapsår bara ha en funktionell profil.

- Skapa en **Teknisk profil för koppling** i **Retail > kanalinställning > räkenskapsintegration > Teknisk profil för koppling** för varje räkenskapskoppling.
  - Välj namnet på en koppling.
  - Välj en kopplingstyp: 
      - **Lokal** - Ange den här typen för fysiska enheter eller program som är installerade på datorn.
      - **Intern** – ange den här typen för kvittoskrivarenheter och tjänster som är anslutna till Retail Server.
      - **Extern** - för externa räkenskapstjänster såsom en webbportal som tillhandahålls av skattemyndigheten.
    
  - Ange inställningar på fliken **anslutning**.

      
 >[!NOTE]
 > En uppdaterad version av en konfiguration som lästes in tidigare laddas för både funktionella och tekniska profiler. Om en rätt anslutning eller dokumentleverantör redan används, meddelas du. Som standard sparas alla ändringar som gjorts manuellt i funktions- och tekniska profiler. För att ignorera dessa profiler med standarduppsättningen med parametrar från en konfiguration, klicka på **uppdatering** på sidan **Funktionsprofiler för koppling** och **Tekniska profiler för koppling**.
 
- Skapa en **räkenskapsregistrering** i **Retail > kanalinställning > räkenskapsintegration > räkenskapsregistrering** för varje unik process i räkenskapsintegreringen. En registreringsprocess definieras av ordningen på registreringsstegen och kopplingsgruppen som används i varje steg. 
  
  - Lägg till registreringsteg i processen:
      - Klicka på **Lägg till**.
      - Välj en kopplingstyp.
      
      >[!NOTE]
      > Det här fältet definierar var systemet söker i en teknisk profil för kopplingen, antingen i maskinvaruprofiler för kopplingstypen **lokal** eller funktionsprofiler för kassa för andra räkenskapskopplingstyper.
      
   - Välj en kopplingsgrupp.
   
     >[!NOTE]
     > Klicka på **Validera** för att kontrollera integriteten hos registreringsprocesstrukturen. Det rekommenderas att valideringar sker i följande fall:
       >- För en ny registreringsprocess när alla inställningarna slutförs, inklusive bindning till funktionsprofiler för kassa och maskinvaruprofiler.
       >- Efter att du uppdaterar en befintlig registreringsprocess.

-  Bind räkenskapsregistreringar till funktionsprofiler för kassa i **Retail > kanalinställningar > kassainställningar > kassaprofiler > funktionsprofiler**.
   - Klicka på **redigera** och välj ett **processnummer** på fliken **räkenskapsregistrering**.
- Bind tekniska kopplingsprofiler till maskinvaruprofiler i **Retail > kanalinställningar > kassainställningar > kassaprofiler > maskinvaruprofiler**.
   - Klickar på **redigera**, klicka på **nytt** på fliken **Teknisk profil för räkenskaper**.
   - Välj en teknisk profil för koppling på fliken **Profilnummer**.
   
     >[!NOTE]
     > Du kan lägga till flera tekniska profiler till en maskinvaruprofil. Men detta stöds inte om en maskinvaruprofil har flera skärningspunkter med någon kopplingsgrupp. Om du vill undvika felaktiga inställningar bör du validera registreringsprocessen när du har uppdaterat alla maskinvaruprofiler.

