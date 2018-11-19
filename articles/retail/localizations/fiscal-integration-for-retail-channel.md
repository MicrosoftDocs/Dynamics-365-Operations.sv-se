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
# <a name="fiscal-integration-for-retail-channel"></a><span data-ttu-id="b629d-103">Räkenskapsintegration för butikskanal</span><span class="sxs-lookup"><span data-stu-id="b629d-103">Fiscal integration for Retail channel</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b629d-104">Det här avsnittet innehåller en översikt över funktioner för räkenskapsintegration i Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="b629d-104">This topic is an overview of the fiscal integration functionality that is available in Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="b629d-105">Funktionen för räkenskapsintegration är ett ramverk som är utformat för att stödja lokala skatteregler som är avsedda att förebygga bedrägeri inom detaljhandel.</span><span class="sxs-lookup"><span data-stu-id="b629d-105">The fiscal integration functionality is a framework designed to support local fiscal laws that are aimed to prevent fraud in the Retail industry.</span></span> <span data-ttu-id="b629d-106">Typiska scenarier som kan omfatta räkenskapsintegration är:</span><span class="sxs-lookup"><span data-stu-id="b629d-106">Typical scenarios that could be covered by using fiscal integration include:</span></span>

- <span data-ttu-id="b629d-107">Skriva ut kvitto och ge det till kunden.</span><span class="sxs-lookup"><span data-stu-id="b629d-107">Printing a fiscal receipt and giving it to the customer.</span></span>
- <span data-ttu-id="b629d-108">Skydda inlämnande av uppgifter som rör försäljning och returer som gjorts i en kassa till en extern tjänst som tillhandahålls av myndigheten.</span><span class="sxs-lookup"><span data-stu-id="b629d-108">Securing the submission of the information related to sales and returns performed on POS to an external service provided by the authority.</span></span>
- <span data-ttu-id="b629d-109">Använda dataskydd med en digital signatur som godkänts av myndigheten.</span><span class="sxs-lookup"><span data-stu-id="b629d-109">Using data protection with a digital signature authorized by the authority.</span></span>

<span data-ttu-id="b629d-110">Det här avsnittet ger riktlinjer för att skapa räkenskapsintegration så att användarna kan utföra följande uppgifter.</span><span class="sxs-lookup"><span data-stu-id="b629d-110">This topic provides guidelines for setting up fiscal integration so users can perform the following tasks.</span></span> 

- <span data-ttu-id="b629d-111">Konfigurera räkenskapskopplingar som är kvittoskrivarenheter eller tjänster som används för räkenskapsregistrering såsom spara, digitala signaturer och skyddad överföring av räkenskapsdata.</span><span class="sxs-lookup"><span data-stu-id="b629d-111">Configure fiscal connectors, which are fiscal devices or services used for fiscal registration purposes like saving, digital signatures, and secured submission of fiscal data.</span></span>
- <span data-ttu-id="b629d-112">Konfigurera dokumentleverantören, som definierar en för utmatningsmetod och en algoritm för generering av skattedokument.</span><span class="sxs-lookup"><span data-stu-id="b629d-112">Configure the document provider, which defines an output method and an algorithm of fiscal document generation.</span></span>
- <span data-ttu-id="b629d-113">Konfigurera räkenskapsregistrering som definierar en följd av steg och en grupp med kontakter som används i varje steg.</span><span class="sxs-lookup"><span data-stu-id="b629d-113">Configure the fiscal registration process, which is defines a sequence of steps and a group of connectors used on each step.</span></span>
- <span data-ttu-id="b629d-114">Tilldela räkenskapsregistrering till funktionsprofiler för kassa.</span><span class="sxs-lookup"><span data-stu-id="b629d-114">Assign fiscal registration processes to POS functionality profiles.</span></span>
- <span data-ttu-id="b629d-115">Tilldela tekniska profiler för koppling, antingen till maskinvaruprofiler (för lokala räkenskapskopplingar) eller till funktionsprofiler för kassa (för andra typer av räkenskapskopplingar).</span><span class="sxs-lookup"><span data-stu-id="b629d-115">Assign connector technical profiles, either to hardware profiles (for the local fiscal connectors) or to POS functionality profiles (for other fiscal connector types).</span></span>

## <a name="fiscal-integration-execution-flow"></a><span data-ttu-id="b629d-116">Räkenskapsintegration körningsflöde</span><span class="sxs-lookup"><span data-stu-id="b629d-116">Fiscal integration execution flow</span></span>
<span data-ttu-id="b629d-117">I följande scenario visar vanligt körningsflöde för räkenskapsintegration.</span><span class="sxs-lookup"><span data-stu-id="b629d-117">The following scenario shows the common fiscal integration execution flow.</span></span>

1. <span data-ttu-id="b629d-118">Initialisering av räkenskapsregistreringen.</span><span class="sxs-lookup"><span data-stu-id="b629d-118">Initialization of the fiscal registration process.</span></span>
  
   <span data-ttu-id="b629d-119">Efter att ha utfört vissa åtgärder där räkenskapsregister krävs, till exempel när en detaljhandelstransaktion har slutförts, är räkenskapsregistreringen associerad med den nuvarande funktionalitetsprofil för kassa.</span><span class="sxs-lookup"><span data-stu-id="b629d-119">After performing some actions where fiscal registration is required, such as after a retail transaction has been concluded, the fiscal registration process is associated with the current POS functionality profile.</span></span>

1. <span data-ttu-id="b629d-120">Sök efter en räkenskapskoppling.</span><span class="sxs-lookup"><span data-stu-id="b629d-120">Search for a fiscal connector.</span></span>
   
   <span data-ttu-id="b629d-121">För varje räkenskapsregistreringssteg i räkenskapsregistreringen matchar systemet listan över räkenskapskopplingar.</span><span class="sxs-lookup"><span data-stu-id="b629d-121">For each fiscal registration step included in the fiscal registration process, the system matches the list of fiscal connectors.</span></span> <span data-ttu-id="b629d-122">Dessa kopplingar har en funktionell profil som ingår i den angivna kopplingsgruppen med en lista över de kopplingar som har en teknisk profil associerad till den aktuella maskinvaruprofilen (för en typ av koppling som endast motsvarar **lokala**) eller med den aktuella funktionsprofilen för kassa (för andra typer av kopplingar).</span><span class="sxs-lookup"><span data-stu-id="b629d-122">These connectors have a functional profile included in the specified connector group, with a list of connectors that have a technical profile associated with the current hardware profile (for a connector type that equals **Local** only) or with the current POS functionality profile (for other connector types).</span></span>
   
1. <span data-ttu-id="b629d-123">Utför räkenskapsintegrationen.</span><span class="sxs-lookup"><span data-stu-id="b629d-123">Perform the fiscal integration.</span></span>

   <span data-ttu-id="b629d-124">Systemet utför alla nödvändiga åtgärder som definieras av en uppsättning kopplade till den hittade kopplingen.</span><span class="sxs-lookup"><span data-stu-id="b629d-124">The system executes all necessary actions defined by an assembly linked with the found connector.</span></span> <span data-ttu-id="b629d-125">Detta görs i enlighet med inställningarna för funktionella profilen och tekniska profilen som hittades i det föregående steget för den här kopplingen.</span><span class="sxs-lookup"><span data-stu-id="b629d-125">This is done in accordance with the settings of the functional profile and technical profile that were found on the previous step for this connector.</span></span>

## <a name="setup-needed-before-using-fiscal-integration"></a><span data-ttu-id="b629d-126">Inställningar behövs innan du använder räkenskapsintegration</span><span class="sxs-lookup"><span data-stu-id="b629d-126">Setup needed before using fiscal integration</span></span>
<span data-ttu-id="b629d-127">Du bör definiera följande inställningar innan du kan använda funktionen räkenskapsintegrering:</span><span class="sxs-lookup"><span data-stu-id="b629d-127">Before using the fiscal integration functionality, you should define the following settings:</span></span>

- <span data-ttu-id="b629d-128">Definiera en nummerserie på sidan **Butiksparametrar** för funktionell profilnummer för räkenskap.</span><span class="sxs-lookup"><span data-stu-id="b629d-128">Define the number sequence on the **Retail parameters** page for the fiscal functional profile number.</span></span>
  
- <span data-ttu-id="b629d-129">Definiera nummersekvens på sidan **Delade butiksparametrar** för följande referenser:</span><span class="sxs-lookup"><span data-stu-id="b629d-129">Define the number sequences on the **Retail shared parameters** page for the following references:</span></span>
  
  - <span data-ttu-id="b629d-130">Nummer för teknisk profil för räkenskaper</span><span class="sxs-lookup"><span data-stu-id="b629d-130">Fiscal technical profile number</span></span>
  - <span data-ttu-id="b629d-131">Gruppnummer för räkenskapskoppling</span><span class="sxs-lookup"><span data-stu-id="b629d-131">Fiscal connector group number</span></span>
  - <span data-ttu-id="b629d-132">Nummer för registreringsprocess</span><span class="sxs-lookup"><span data-stu-id="b629d-132">Registration process number</span></span>

- <span data-ttu-id="b629d-133">Skapa en **räkenskapskoppling** i **Retail > kanalinställning > räkenskapsintegration > räkenskapskopplingar** för varje enhet eller tjänst som du tänker använda för räkenskapsintegration.</span><span class="sxs-lookup"><span data-stu-id="b629d-133">Create a **Fiscal connector** in **Retail > Channel setup > Fiscal integration > Fiscal connectors** for each device or service that you plan to use for fiscal integration purposes.</span></span>

-  <span data-ttu-id="b629d-134">Skapa en **skattedokumentleverantör** i **Retail > kanalinställning > räkenskapsintegration > leverantörer av skattedokument** för alla räkenskapskopplingar.</span><span class="sxs-lookup"><span data-stu-id="b629d-134">Create a **Fiscal document provider** in **Retail > Channel setup > Fiscal integration > Fiscal document providers** for all fiscal connectors.</span></span> <span data-ttu-id="b629d-135">Datamappning betraktas som en del av skattedokumentleverantören.</span><span class="sxs-lookup"><span data-stu-id="b629d-135">Data mapping is considered a part of the fiscal document provider.</span></span> <span data-ttu-id="b629d-136">Om du vill ställa in olika datamappningar för samma typ av koppling (till exempel delstatsspecifika regler) bör du skapa olika leverantörer för skattedokument.</span><span class="sxs-lookup"><span data-stu-id="b629d-136">To set up different data mappings for the same connector (like state-specific regulations), you should create different fiscal document providers.</span></span>

- <span data-ttu-id="b629d-137">Skapa en **Funktionsprofil för koppling** i **Retail > kanalinställning > räkenskapsintegration > Funktionsprofil för koppling** för varje leverantör av skattedokument.</span><span class="sxs-lookup"><span data-stu-id="b629d-137">Create a **Connector functional profile** in **Retail > Channel setup > Fiscal integration > Connector functional profiles** for each fiscal document provider.</span></span>
  - <span data-ttu-id="b629d-138">Välj namnet på en koppling.</span><span class="sxs-lookup"><span data-stu-id="b629d-138">Select a connector name.</span></span>
  - <span data-ttu-id="b629d-139">Välj en dokumentleverantör.</span><span class="sxs-lookup"><span data-stu-id="b629d-139">Select a document provider.</span></span>
  - <span data-ttu-id="b629d-140">Ange momsinställningar på fliken **tjänstinställning**.</span><span class="sxs-lookup"><span data-stu-id="b629d-140">Specify VAT rates settings on the **Service setup** tab.</span></span>
  - <span data-ttu-id="b629d-141">Ange momskodmappning och betalningsmedeltypmappning på fliken **Datamappning**.</span><span class="sxs-lookup"><span data-stu-id="b629d-141">Specify VAT codes mapping and tender type mapping on the **Data mapping** tab.</span></span>

  #### <a name="examples"></a><span data-ttu-id="b629d-142">Exempel</span><span class="sxs-lookup"><span data-stu-id="b629d-142">Examples</span></span> 

  |  | <span data-ttu-id="b629d-143">Format</span><span class="sxs-lookup"><span data-stu-id="b629d-143">Format</span></span> | <span data-ttu-id="b629d-144">Exempel</span><span class="sxs-lookup"><span data-stu-id="b629d-144">Example</span></span> | 
  |--------|--------|--------|
  | <span data-ttu-id="b629d-145">Inställning av momssatser</span><span class="sxs-lookup"><span data-stu-id="b629d-145">VAT rates settings</span></span> | <span data-ttu-id="b629d-146">värde: VATrate</span><span class="sxs-lookup"><span data-stu-id="b629d-146">value : VATrate</span></span> | <span data-ttu-id="b629d-147">1 : 2000, 2 : 1800</span><span class="sxs-lookup"><span data-stu-id="b629d-147">1 : 2000, 2 : 1800</span></span> |
  | <span data-ttu-id="b629d-148">Mappning av momskoder</span><span class="sxs-lookup"><span data-stu-id="b629d-148">VAT codes mapping</span></span> | <span data-ttu-id="b629d-149">VATcode : värde</span><span class="sxs-lookup"><span data-stu-id="b629d-149">VATcode : value</span></span> | <span data-ttu-id="b629d-150">vat20 : 1, vat18 : 2</span><span class="sxs-lookup"><span data-stu-id="b629d-150">vat20 : 1, vat18 : 2</span></span> |
  | <span data-ttu-id="b629d-151">Mappning av betalningsmedelstyper</span><span class="sxs-lookup"><span data-stu-id="b629d-151">Tender types mapping</span></span> | <span data-ttu-id="b629d-152">TenderTyp: värde</span><span class="sxs-lookup"><span data-stu-id="b629d-152">TenderTyp : value</span></span> | <span data-ttu-id="b629d-153">Kontant: 1 kort: 2</span><span class="sxs-lookup"><span data-stu-id="b629d-153">Cash : 1, Card : 2</span></span> |

- <span data-ttu-id="b629d-154">Skapa **Grupper för räkenskapskoppling** i **Retail > kanalinställning > räkenskapsintegration > grupp för räkenskapskoppling**.</span><span class="sxs-lookup"><span data-stu-id="b629d-154">Create **Fiscal connector groups** in **Retail > Channel setup > Fiscal integration > Fiscal connector group**.</span></span> <span data-ttu-id="b629d-155">En kopplingsgrupp som är en delmängd av funktionella profiler länkas till räkenskapskopplingar som utför identiska funktioner som används i samma fas inom en räkenskapsregistrering.</span><span class="sxs-lookup"><span data-stu-id="b629d-155">A connector group is a subset of functional profiles linked with fiscal connectors that perform identical functions and are used at the same stage within a fiscal registration process.</span></span>

   - <span data-ttu-id="b629d-156">Lägg till funktionella profiler till kopplingsgruppen.</span><span class="sxs-lookup"><span data-stu-id="b629d-156">Add functional profiles to the connector group.</span></span> <span data-ttu-id="b629d-157">Klicka på **Lägg till** på sidan **funktionella profiler** och välj ett profilnummer.</span><span class="sxs-lookup"><span data-stu-id="b629d-157">Click **Add** on the **Functional profiles** page and select a profile number.</span></span>
   - <span data-ttu-id="b629d-158">Om du vill skjuta upp förbrukningen av funktionella profilen, ange **inaktivera** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="b629d-158">If you want to suspend usage of the functional profile, set **Disable** to **Yes**.</span></span> 
   
     <span data-ttu-id="b629d-159">Denna ändring påverkar endast aktuella kopplingsgruppen.</span><span class="sxs-lookup"><span data-stu-id="b629d-159">This change affects the current connector group only.</span></span> <span data-ttu-id="b629d-160">Du kan fortsätta att använda samma funktionella profil i andra kopplingsgrupper.</span><span class="sxs-lookup"><span data-stu-id="b629d-160">You can continue using the same functional profile in other connector groups.</span></span>

     >[!NOTE]
     > <span data-ttu-id="b629d-161">Inom en kopplingsgrupp kan varje räkenskapsår bara ha en funktionell profil.</span><span class="sxs-lookup"><span data-stu-id="b629d-161">Within a connector group, each fiscal connector can only have one functional profile.</span></span>

- <span data-ttu-id="b629d-162">Skapa en **Teknisk profil för koppling** i **Retail > kanalinställning > räkenskapsintegration > Teknisk profil för koppling** för varje räkenskapskoppling.</span><span class="sxs-lookup"><span data-stu-id="b629d-162">Create a **Connector technical profile** in **Retail > Channel setup > Fiscal integration > Connector technical profiles** for each fiscal connector.</span></span>
  - <span data-ttu-id="b629d-163">Välj namnet på en koppling.</span><span class="sxs-lookup"><span data-stu-id="b629d-163">Select a connector name.</span></span>
  - <span data-ttu-id="b629d-164">Välj en kopplingstyp:</span><span class="sxs-lookup"><span data-stu-id="b629d-164">Select a connector type:</span></span> 
      - <span data-ttu-id="b629d-165">**Lokal** - Ange den här typen för fysiska enheter eller program som är installerade på datorn.</span><span class="sxs-lookup"><span data-stu-id="b629d-165">**Local** - Set this type for physical devices or applications installed on a local machine.</span></span>
      - <span data-ttu-id="b629d-166">**Intern** – ange den här typen för kvittoskrivarenheter och tjänster som är anslutna till Retail Server.</span><span class="sxs-lookup"><span data-stu-id="b629d-166">**Internal** - Set this type for fiscal devices and services connected to Retail Server.</span></span>
      - <span data-ttu-id="b629d-167">**Extern** - för externa räkenskapstjänster såsom en webbportal som tillhandahålls av skattemyndigheten.</span><span class="sxs-lookup"><span data-stu-id="b629d-167">**External** - For external fiscal services like a web-portal provided by a tax authority.</span></span>
    
  - <span data-ttu-id="b629d-168">Ange inställningar på fliken **anslutning**.</span><span class="sxs-lookup"><span data-stu-id="b629d-168">Specify settings on the **Connection** tab.</span></span>

      
 >[!NOTE]
 > <span data-ttu-id="b629d-169">En uppdaterad version av en konfiguration som lästes in tidigare laddas för både funktionella och tekniska profiler.</span><span class="sxs-lookup"><span data-stu-id="b629d-169">An updated version of a configuration that was loaded earlier will be loaded for both functional and technical profiles.</span></span> <span data-ttu-id="b629d-170">Om en rätt anslutning eller dokumentleverantör redan används, meddelas du.</span><span class="sxs-lookup"><span data-stu-id="b629d-170">If an appropriate connector or document provider is already in use, you will be notified.</span></span> <span data-ttu-id="b629d-171">Som standard sparas alla ändringar som gjorts manuellt i funktions- och tekniska profiler.</span><span class="sxs-lookup"><span data-stu-id="b629d-171">By default, all changes that have been made manually in functional and technical profiles will be stored.</span></span> <span data-ttu-id="b629d-172">För att ignorera dessa profiler med standarduppsättningen med parametrar från en konfiguration, klicka på **uppdatering** på sidan **Funktionsprofiler för koppling** och **Tekniska profiler för koppling**.</span><span class="sxs-lookup"><span data-stu-id="b629d-172">In order to override these profiles with the default set of parameters from a configuration, click **Update** on the **Connector functional profiles** page and **Connector technical profiles** page.</span></span>
 
- <span data-ttu-id="b629d-173">Skapa en **räkenskapsregistrering** i **Retail > kanalinställning > räkenskapsintegration > räkenskapsregistrering** för varje unik process i räkenskapsintegreringen.</span><span class="sxs-lookup"><span data-stu-id="b629d-173">Create a **Fiscal registration process** in **Retail > Channel setup > Fiscal integration > Fiscal registration processes** for each unique process of the fiscal integration.</span></span> <span data-ttu-id="b629d-174">En registreringsprocess definieras av ordningen på registreringsstegen och kopplingsgruppen som används i varje steg.</span><span class="sxs-lookup"><span data-stu-id="b629d-174">A registration process is defined by the sequence of the registration steps and the connector group used on each step.</span></span> 
  
  - <span data-ttu-id="b629d-175">Lägg till registreringsteg i processen:</span><span class="sxs-lookup"><span data-stu-id="b629d-175">Add registration steps to the process:</span></span>
      - <span data-ttu-id="b629d-176">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="b629d-176">Click **Add**.</span></span>
      - <span data-ttu-id="b629d-177">Välj en kopplingstyp.</span><span class="sxs-lookup"><span data-stu-id="b629d-177">Select a connector type.</span></span>
      
      >[!NOTE]
      > <span data-ttu-id="b629d-178">Det här fältet definierar var systemet söker i en teknisk profil för kopplingen, antingen i maskinvaruprofiler för kopplingstypen **lokal** eller funktionsprofiler för kassa för andra räkenskapskopplingstyper.</span><span class="sxs-lookup"><span data-stu-id="b629d-178">This field defines where the system will search in a technical profile for the connector, either in hardware profiles for connector type **Local**, or in POS functionality profiles for other fiscal connector types.</span></span>
      
   - <span data-ttu-id="b629d-179">Välj en kopplingsgrupp.</span><span class="sxs-lookup"><span data-stu-id="b629d-179">Select a connector group.</span></span>
   
     >[!NOTE]
     > <span data-ttu-id="b629d-180">Klicka på **Validera** för att kontrollera integriteten hos registreringsprocesstrukturen.</span><span class="sxs-lookup"><span data-stu-id="b629d-180">Click **Validate** to check the integrity of the registration process structure.</span></span> <span data-ttu-id="b629d-181">Det rekommenderas att valideringar sker i följande fall:</span><span class="sxs-lookup"><span data-stu-id="b629d-181">It’s recommended that validations be made in the following cases:</span></span>
       >- <span data-ttu-id="b629d-182">För en ny registreringsprocess när alla inställningarna slutförs, inklusive bindning till funktionsprofiler för kassa och maskinvaruprofiler.</span><span class="sxs-lookup"><span data-stu-id="b629d-182">For a new registration process after all the settings are completed, including binding to POS functionality profiles and hardware profiles.</span></span>
       >- <span data-ttu-id="b629d-183">Efter att du uppdaterar en befintlig registreringsprocess.</span><span class="sxs-lookup"><span data-stu-id="b629d-183">After making updates to an existing registration process.</span></span>

-  <span data-ttu-id="b629d-184">Bind räkenskapsregistreringar till funktionsprofiler för kassa i **Retail > kanalinställningar > kassainställningar > kassaprofiler > funktionsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="b629d-184">Bind fiscal registration processes to POS functionality profiles in **Retail > Channel setup > POS setup > POS profiles > Functionality profiles**.</span></span>
   - <span data-ttu-id="b629d-185">Klicka på **redigera** och välj ett **processnummer** på fliken **räkenskapsregistrering**.</span><span class="sxs-lookup"><span data-stu-id="b629d-185">Click **Edit** and select a **Process number** on the **Fiscal registration process** tab.</span></span>
- <span data-ttu-id="b629d-186">Bind tekniska kopplingsprofiler till maskinvaruprofiler i **Retail > kanalinställningar > kassainställningar > kassaprofiler > maskinvaruprofiler**.</span><span class="sxs-lookup"><span data-stu-id="b629d-186">Bind the connector technical profiles to the hardware profiles in **Retail > Channel setup > POS setup > POS profiles > Hardware profiles**.</span></span>
   - <span data-ttu-id="b629d-187">Klickar på **redigera**, klicka på **nytt** på fliken **Teknisk profil för räkenskaper**.</span><span class="sxs-lookup"><span data-stu-id="b629d-187">Click **Edit**, then click **New** on the **Fiscal technical profile** tab.</span></span>
   - <span data-ttu-id="b629d-188">Välj en teknisk profil för koppling på fliken **Profilnummer**.</span><span class="sxs-lookup"><span data-stu-id="b629d-188">Select a connector technical profile in the **Profile number** field.</span></span>
   
     >[!NOTE]
     > <span data-ttu-id="b629d-189">Du kan lägga till flera tekniska profiler till en maskinvaruprofil.</span><span class="sxs-lookup"><span data-stu-id="b629d-189">You can add several technical profiles to a hardware profile.</span></span> <span data-ttu-id="b629d-190">Men detta stöds inte om en maskinvaruprofil har flera skärningspunkter med någon kopplingsgrupp.</span><span class="sxs-lookup"><span data-stu-id="b629d-190">However, this is not supported if a hardware profile has more than one intersection with any connector group.</span></span> <span data-ttu-id="b629d-191">Om du vill undvika felaktiga inställningar bör du validera registreringsprocessen när du har uppdaterat alla maskinvaruprofiler.</span><span class="sxs-lookup"><span data-stu-id="b629d-191">To avoid incorrect settings, it’s recommended that you validate the registration process after updating all the hardware profiles.</span></span>

