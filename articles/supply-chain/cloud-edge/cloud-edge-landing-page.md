---
title: Moln- och kantskalningsenheter för arbetsbelastning i tillverknings och distributionslagerhantering
description: Detta ämne ger information, se moln och kantskalningsenhet med arbetsbelastning för tillverkning och distributionslagerhantering.
author: cabeln
manager: ''
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: cabeln
ms.search.validFrom: 2020-09-23
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 28301cdfb86d00ea6f04e996fe7fb1485e83b2d4
ms.sourcegitcommit: 289e9183d908825f4c8dcf85d9affd4119238d0c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104974"
---
# <a name="cloud-and-edge-scale-units-for-manufacturing-and-warehouse-management-workloads"></a>Moln- och kantskalningsenheter för arbetsbelastning i tillverknings och distributionslagerhantering

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Moln- och kantskalningsenheter möjliggör distribution av arbetsbelastning för arbetsstyrning och körning av lagerställen i olika miljöer. Med hjälp av den här funktionen kan du förbättra prestanda, förhindra avbrott i tjänsten och maximera drifttiden. Följande tillägg är tillgängliga:

- Tillägg för molnskalningsenhet för Dynamics 365 Supply Chain Management
- Tillägg för kantskalningsenhet för Dynamics 365 Supply Chain Management

Företag som arbetar med tillverkning och distribution måste kunna köra viktiga affärsprocesser dygnet runt, utan avbrott och i skala. Moln- och kantskalningsenheter kan företag köra viktiga verksamhets kritiska tillverknings- och lagerprocesser utan avbrott, även om de är i drift med tillfälliga nätverksanslutnings- eller latensproblem.

## <a name="public-preview-information"></a>Allmän information om förhandsgranskning

Förhandsgranskningen ger en miljö som fungerar som ett molnbaserad nav i din Dynamics 365 Supply Chain Management-miljö och en miljö som fungerar som en molnskalningsenhet.

<!-- You will also be able to use Local Business Data (LBD) to configure an on-premises environment as an edge scale unit for the hub you received as part of the preview program.-->

### <a name="preview-availability"></a>Förhandsgranska tillgänglighet

Förhandsgranskningen av moln- och kantskalningsenheter blir tillgänglig för befintliga kunder för Supply Chain Management i oktober 2020.

Om du vill få tillgång till den förhandsversionen från oktober 10.0.15/plattformsuppdatering 39 för distribution i din [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/v2)-miljö måste du vara en del av programmet för förhandsgranskning (kallas även PEAP) för Supply Chain Management. Du kan ansluta till PEAP om du redan är medlem i fler än ett bredare [Dynamics Insider Program](https://experience.dynamics.com/insider). Markera bara det program som heter "Finance and Operations: program för förhandsversionen (PEAP)".

> [!IMPORTANT]
> Funktionen för skalbara enheter för Supply Chain Management är bara tillgänglig om du godkänner [förhandsgranskning av moln + kant för varje Finance and Operations villkor](https://Aka.ms/SCMCnETerms).

### <a name="data-processing-for-the-preview"></a>Databehandling för förhandsgranskning

Under den allmänna förhandsgranskningen kommer vissa hanteringstjänster endast att finnas i USA. Om funktionen blir allmänt tillgänglig kommer dessa hanteringstjänster emellertid att vara tillgängliga i alla de geografier som stöds av tillhandahållare av Supply Chain Management. Detta påverkar överföring och lagring av den administrativa information som används av skalningsenhetsansvarige, bland annat:

- Namn och ID för innehavare
- Ditt LCS projekt-ID
- Administratörsmeddelanden som används för att logga in
- Miljö-ID för nav- och skalningsenheter
- Konfigurationer av arbetsbelastning
- Insamlade mått (t.ex. svarstid och dataflöde) som visas på kartanalyssidan

Data som överförs till och lagras i amerikanska datacenter tas bort när dina förhandsgranskningsmiljöer stängs av.

### <a name="sign-up-for-the-preview"></a>Registrera för förhandsversionen

Om du vill registrera dig för förhandsgranskning av moln och kant för Supply Chain Management måste din organisation redan ha en molnmiljö för direkt molnmiljö för Supply Chain Management.

Skalningsenhets kapacitet är för närvarande i offentlig förhandsgranskning. När du registrerar dig måste du använda ett användarkonto på den specifika innehavaren. Du måste också vara projektägare eller en miljöadministratör i LCS för ett aktivt Dynamics 365 LCS-projekt i den innehavaren.

När du registrerar dig för förhandsgranskningen väljer du en innehavare och går igenom registreringsstegen. Så snart Microsoft kan tilldela förhandsgranskningskapacitet skickar vi ett e-postmeddelande som innehåller information om etableringen och kampanjkoderna för två miljöer (ett nav och en skalningsenhet) för lämpligt LCS-projekt. Du kan sedan distribuera de två miljöerna som begränsade miljöer i nivå 2. Dessa miljöer kommer att vara giltiga 60 dagar efter kampanjkodernas skapelsedatum. Du bör inte använda de två miljöerna förrän steget som beskrivs i nästa stycke har slutförts.

När du har bekräftat med Microsoft att de två miljöerna har distribuerats med hjälp av kampanjkoderna kommer en av miljöerna att konfigureras för att fungera som ett nav och den andra kommer att konfigureras att fungera som en skalningsenhet. Du kan sedan konfigurera enheterna och driftsätta valda arbetsbelastningar för lagerstyrning och tillverkning med hjälp av [portalen skalningsenhetsansvarig](https://aka.ms/SCMSUM).

Förhandsgranskningsmiljöer tas automatiskt bort efter 60 dagar. Men de kan tas bort tidigare om det verkar som de inte används. När du har tagit bort dina förhandsgranskningsmiljöer kan du registrera dig och skapa en ny förhandsgranskningsdistribution.

Om du vill registrera dig för förhandsgranskningen går du till [portalen för skalningsenhetsansvarig](https://aka.ms/SCMSUM).

### <a name="limitations-that-apply-during-the-preview-period"></a>Begränsningar som gäller under förhandsgranskningsperioden

> [!IMPORTANT]
> För den första fasen av den här funktionen förhandsversion har Microsoft endast stöd för nav med molnskalningsenheter, inte nav med kantskalningsenheter. Kantskalningsenheter installeras lokalt och förväntas bli tillgängliga under en kommande fas i programmet.

Eftersom moln- och kantskalningsenheter är en förhandsvisningsfunktion, är tjänster som är relaterade till dem tillgängliga för närvarande i begränsade länder och regioner. Genom att aktivera moln- och kantskalningsenheter bekräftar du att du förstår att vissa data som är relaterade till konfigurationen och bearbetningen av moln- och kantskalningsenheter kan lagras i ett datacenter som finns i USA. Om du aktiverar moln- och kantskalningsenheter samtycker du också till [förhandsgranskningen av moln + kant Finance and Operations villkor](https://Aka.ms/SCMCnETerms). Mer information om moln- och kantskalningsenheter finns i [dokumentationen](https://aka.ms/scmcne).

Din integritet är viktig för Microsoft. För mer information läs vår [sekretesspolicy](https://aka.ms/privacy).

> [!IMPORTANT]
> Vissa företagsfunktioner stöds inte fullt ut i den allmänna förhandsgranskningen när arbetsbelastningar används på skalningsenheter. Mer information om funktionella arbetsbelastningar finns i avsnitten senare i det här avsnittet.

## <a name="scale-units-and-dedicated-workloads"></a>Skalningsenheter och dedikerade arbetsbelastning

:::image type="content" source="./media/cloud_edge-HeroDiagram.png" alt-text="Dynamics 365 med skalningsenheter":::

Skalningsenheter utökas med Supply Chain Management navmiljö genom att lägga till dedikerad bearbetningskapacitet. Skalningsenheter kan köras i molnet. De kan också köras på kanten av dina lokala lokaler. Skalningsenheter kan tillfälligt kopplas från navmiljön. När de är anslutna får enheten all information som behövs för att köra den dedikerade bearbetningen för tilldelade arbetsuppgifter.

:::image type="content" source="media/cloud_edge-previewoptions.png" alt-text="Alternativ för skalningsenhet i allmänt tillgänglig förhandsversion":::

För den allmänna förhandsgranskningen kan du konfigurera en navmiljö med valda arbetsbelastningar på en molnskalningsenhet med hjälp av portalen skalningsenhetsansvarig. Förhandsgranska deltagare som har åtkomst till en lokal affärsdatamiljö (LBD) kan också konfigurera LBD-miljön som en kantskalningsenhet.

Ett arbetsflöde är en definierad uppsättning av affärsfunktioner som kan utsättas för att delegeras till en skalningsenhet. För närvarande har förhandsgranskningsfunktionerna två typer av arbetsbelastning:

- Tillverkningskörning
- Lagerstyrning

Du kan tilldela en av varje typ av arbetsbelastning per skalningsenhet. 

### <a name="dedicated-manufacturing-execution-workload-capabilities-in-a-scale-unit"></a>Särskilda arbetsbelastningsmöjligheter för tillverkningskörning i en skalningsenhet

För tillverkningskörning ger skalenheter för moln och kant följande funktioner, även om kantenheterna inte är anslutna till molnet:

- Maskinoperatörer och arbetsledare kan komma åt den operationella produktionsplanen.
- Maskinoperatörer kan hålla planen aktuell genom att köra separata jobb för bearbetning och processtillverkning.
- Arbetsledaren kan justera driftsplanen.
- Arbetare kan få åtkomst till tid och närvaro för in- och utstämpling i kanten, för att säkerställa korrekt löneberäkning för arbetare.

Mer information finns i [detaljerna för tillverkningsskalenheten](cloud-edge-workload-manufacturing.md).

### <a name="dedicated-warehouse-management-workload-capabilities-in-a-scale-unit"></a>Särskilda arbetsbelastningsmöjligheter för distributionslagerhantering i en skalningsenhet

För distributionslagerhantering ger skalenheter för moln och kant följande funktioner, även om kantenheterna inte är anslutna till molnet:

- Bearbetning av valda påfyllningsmetoder aktiveras för försäljningsorder och påfyllnad baserad på efterfrågan.
- Lagerarbetare kan köra lagerställearbete för försäljnings- och efterfrågepåfyllning genom att använda distributionslagerappen.
- Lagerarbetare kan fråga om lagerbehållning genom att använda distributionslagerappen.
- Lagerarbetare kan skapa och köra lagerrörelser genom att använda distributionslagerappen.
- Lagerarbetare kan registrera inköpsorder och utföra inlagringsarbete med hjälp av distributionslagerappen.

Mer information finns i [detaljerna för lagerställe skalenheten](cloud-edge-workload-warehousing.md).

## <a name="onboard-scale-units-for-your-supply-chain-management-environment"></a>Enheter med inbyggda skalningsenheter för din Supply Chain Management-miljö

### <a name="deploy-the-preview-for-cloud-and-edge-scale-units"></a>Distribuera förhandsgranskningen för moln- och kantskalningsenheter

Följande illustration visar registrerings- och etableringsflödet för den offentliga förhandsgranskningen för molnskalningsenheter.

:::image type="content" source="media/cloud_edge-previewsignup.png" alt-text="Förhandsgranska anmälningssteg":::

### <a name="select-your-lcs-project-tenant-and-the-detailed-preview-process"></a>Välj klientorganisation för LCS och detaljerad förhandsgranskningsprocess

I den allmänna förhandsgranskningen visar [portal för skalningsenhetsansvarig](https://aka.ms/SCMSUM) listan över de innehavare som ditt konto tillhör, och där du är en ägare eller en miljöadministratör för ett LCS-projekt.

Om innehavaren som du söker efter inte finns med i listan går du till [LCS](https://lcs.dynamics.com/v2) och kontrollerar att du är antingen en miljöadministratör eller en projektägare av LCS-projektet för den innehavaren. Observera att endast Azure Active Directory (Azure AD) konton från den valda innehavaren har behörighet att genomföra anmälan.

> [!NOTE]
> När du har tillämpat ändringarna på LCS kan det ta upp till 30 minuter innan listan över de innehavare som avspeglar ändringarna har tillämpats.

För varje innehavare visas status för anmälan i listan.

:::image type="content" source="media/cloud_edge-Signup1.png" alt-text="Registreringsalternativ för en klientorganisation":::

Välj länken **Klicka här om du vill registrera** för att kunna delta i förhandsgranskningen hos din LCS-klientorganisation. Du måste acceptera villkoren. Du måste också ange en e-postadress till företaget där Microsoft kan skicka meddelanden som är relaterade till förhandsgranskningsprocessen.

:::image type="content" source="media/cloud_edge-Signup2.png" alt-text="Skicka registrering för en klientorganisation":::

Microsoft kommer att granska din begäran och informera dig om nästa steg genom att skicka ett e-postmeddelande till adressen som du har angett i formuläret för registrering.

När du har beviljats åtkomst till förhandsgranskningsprogrammet visas två kampanjkoder för ditt LCS-projekt. Du kan nu använda dessa kampanjkoder för att distribuera två miljöer i LCS. Dessa miljöer måste använda PEAP version 10.0.15 eller senare. När du har tillämpat kampanjkoderna meddelar du Microsoft (enligt anvisningarna) så att vi kan slutföra aktiveringen av miljöer för förhandsgranskningsfunktionerna. Microsoft kommer att meddela dig när det här konfigurationssteget är slutfört.

Du kan nu börja med att konfigurera skalningsenheter och arbetsbelastningar i förhandsgranskningsmiljön.

> [!IMPORTANT]
> När du konfigurerar skalningsenheter för moln kan du [utföra alla steg som behövs på portalen för skalningsenhetsansvarig](#scale-unit-manager-portal).
<!-- 
> If want to use edge scale units with your preview deployment, you must do all scale unit configuration in the user interface on the hub as described in [Configure the hub environment for use with edge scale units](cloud-edge-edge-scale-units-lbd.md#configure-the-hub-environment). You can't use Scale Unit Manager portal if you include an edge scale unit. -->

### <a name="manage-cloud-scale-units-and-workloads-by-using-the-scale-unit-manager-portal"></a><a name="scale-unit-manager-portal"></a>Hantera molnskalningsenheter och arbetsbelastningar med hjälp av portalen för skalningsenhetsansvarig

Gå till [portalen för skalningsenhetsansvarig](https://aka.ms/SCMSUM) och logga in med ditt klientkonto. På sidan **Konfigurera skalningsenheter** kan du lägga till en navmiljö om den inte redan finns med i listan. Du kan sedan välja det nav som du vill konfigurera med enheter och arbetsbelastningar.

:::image type="content" source="media/cloud_edge-Manage.png" alt-text="Skalningsenhet och arbetsbelastningshantering":::

Om du vill lägga till en eller flera skalningsenheter som är tillgängliga i din topologi väljer du **Lägg till skalningsenheter**. I förhandsgranskningen ska du se den molnskalningsenhet som du har distribuerat från en av de kampanjkoder som du har fått som en del av förhandsgranskningsprogrammet.

<!--  [!IMPORTANT]
> In the public preview, the Scale Unit Manager portal shows the cloud scale unit that you received as part of the preview program. Any edge scale unit that you created based on an LBD configuration can't be managed in the Scale Unit Manager portal yet. For configuration details, see [Deploy custom edge scale units on custom hardware using LBD](cloud-edge-edge-scale-units-lbd.md) -->

På fliken **definierade arbetsbelastningar** använder du knappen **Skapa arbetsbelastning** för att lägga till en lagerhanterings- eller tillverkningsarbetsbelastning i en av dina skalningsenheter. För varje arbetsbelastning måste du ange kontexten för de processer som ska ägas av arbetsbelastningen. För distributionslagerhantering arbetsbelastningar är sammanhanget ett specifikt lagerställe på en specifik webbplats och juridisk person. För arbetsbelastningar för tillverkningskörning är sammanhanget en specifik webbplats i en juridisk person.

:::image type="content" source="media/cloud_edge-DefineWorkload.png" alt-text="Skapa arbetsbelastning":::

> [!IMPORTANT]
> Portalen för skalningsenhetsansvarig i förhandsgranskningen låter dig inte ta bort arbetsbelastningar från skalningsenheter eller ta bort tilldelning av en skalningsenhet från ett nav efter att tilldelningen har gjorts. Om du måste ta bort en tilldelning kontaktar du kontaktpersonen för att se hanteringen av förhandsgranskningsprogrammet.

<!-- ### Create an edge scale unit using your custom on-premises hardware appliance

In the public preview, you can create on-premises edge scale units on your custom hardware using the LBD environments. For details, see [Deploy custom edge scale units on custom hardware using LBD](cloud-edge-edge-scale-units-lbd.md). -->
