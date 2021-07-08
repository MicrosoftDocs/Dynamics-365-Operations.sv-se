---
title: Skapande av fraktbehållare
description: I det här avsnittet beskrivs hur du automatiserar skapandet av behållare för last. Med automatiskt skapande av behållare skapas behållare och plockarbete för leveranser när en påfyllnad bearbetas.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable, WHSContainerizatonHistory, WHSContainerPackingPolicyChange, WHSManifestShipmentContainers, WHSAllowedContainerTypeGroup, WHSPostMethod, WHSContainerCreateDialog, WHSContainerCloseDiag, WHSContainer
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 88e38989e3d3e46d0c43779659bc6ea2e29f08e2
ms.sourcegitcommit: 8e846b52763f90d2232ec7d427839f4722570bce
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "6292747"
---
# <a name="containerization"></a>Skapande av fraktbehållare

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du automatiserar skapandet av behållare för last. Med automatiskt skapande av behållare skapas behållare och plockarbete för leveranser när en påfyllnad bearbetas.

Om du vill ställa in skapande av behållare måste du skapa följande:

- **Behållartyp** - Definiera fysiska egenskaper för behållarna. Använd behållaretyper för att paketera lagerartiklar i en viss typ och storlek av förpackningsmaterial, till exempel bingar och lastpallar.
- **Behållargrupper** - Skapa grupper av liknande behållartyper. En behållargrupp kan till exempel inkludera behållartyper som har liknande dimensioner. En behållargrupp anger i vilken ordning behållarna packas och fyllnadsprocenten för varje behållare.
- **Skapa mall för behållare** - skapa mallar som definierar regler för skapande av behållare. Regler för blandat lagret och andra förpackningsstrategier till exempel.
- **Påfyllnadsmallar** – Ställ in en eller flera påfyllnadsmallar om du vill skapa plockarbete för skapande av behållare.

## <a name="create-wave-templates-for-containerization"></a>Skapa påfyllnadsmallar för skapande av behållare

Du måste ställa in en eller flera påfyllnadsmallar på leverans för skapande av behållare. Påfyllnadsmallar innehåller villkor som fastställer följande:

- Hur du bearbetar påfyllnader. Detta kan vara antingen manuellt eller automatiskt.
- Hur du skapar plockningsarbete. Detta avgörs av påfyllnadsmetoderna. Påfyllnadsmallen måste inkludera metoden för **skapande av behållare** .
- Hur du matchar artiklar eller allokeringsrader med en påfyllnad.

Mer information finns i [Påfyllnadsmallar](wave-templates.md).

## <a name="create-container-types"></a>Skapa behållartyper

Använd behållartyper för att skapa beskrivningar av behållare, inklusive högsta värden för fysiska dimensioner och viktkapacitet. När en när en påfyllnad med skapande av behållare bearbetas, skapas behållarna baserat på behållartypinformationen.

Så här ställer du in en behållartyp:

1. Gå till **Warehouse management** \> **Inställningar** \> **Behållare** \> **Behållartyp**.
1. Skapa en ny behållartyp genom att välja **Nytt**.
1. Ange en unik identifierare (ID) och en beskrivning för behållartypen.
1. Ange behållarens verkliga eller beräknade vikt i fältet **Taravikt**.
1. Ange den högsta vikten som behållaren kan bära i fältet **Maximal vikt**.
1. I fälten **Maximal volym för skapande av behållare**, **Maximal längd för skapande av behållare**, **Maximal bredd för skapande av behållare** och **Maximal höjd för skapande av behållare** anger du behållarens fysiska dimensioner.

    > [!NOTE]
    > Värdena för längd och bredd är utbytbara. Detta innebär att du kan rotera artiklar i sidled, eller på x-axeln, om det behövs. Om till exempel längden är 2 m och bredden är 1 m kan du ändra längden till 1 m och bredden till 2 m. Observera att detta inte gäller för höjddimensionen. Du kan inte ändra höjdvärdet för att rotera en artikel vertikalt.

1. Välj anpassade attributvärden för containern i fälten för attribut. Attribut är anpassade värden som används för att filtrera eller sortera artiklar baserat på ett värde som annars inte är tillgängligt. Om du till exempel vill packa artiklar för en viss kund, kan du skapa ett attribut för kundens namn. Du kan skapa attribut på sidan **Behållarattribut**.

## <a name="create-container-groups"></a>Skapa behållargrupper

Du kan ställa in logiska grupper av behållartyper. För varje grupp kan du ange i vilken ordning som behållarna packas och procentsatsen för behållarna som ska fyllas. Artikelns storleksdimensioner avgör om den kommer att passa i en behållare. Den behållare som är närmast artikelns storlek används. Om du har flera behållartyper i en grupp, rekommenderar vi att sekvensen ordnas efter storlek, så att den största, är den första nummer 1 i sekvensen, och den mest minsta behållaren är den sista.

Så här ställer du in en behållargrupp:

1. Gå till **Warehouse management** \> **Inställningar** \> **Behållare** \> **Behållargrupper**.
1. Välj **Nytt** för att skapa en behållargrupp.
1. Ange ett unikt ID och en beskrivning för behållargruppen.
1. På snabbfliken **Detaljer**, välj **Ny** för att lägga till en behållartyp i gruppen.
1. Ange en behållartyp i fältet **Behållartypkod**.
1. Välj **Flytta upp** eller **Flytta ned** om du vill ange den ordning i vilken behållartyperna packas.

## <a name="create-container-build-templates"></a>Skapa mallar för behållarversion

Du kan ställa in regler för processen att skapa behållare, till exempel blandande regler för kvantiteten och andra emballagestrategier. Du kan till exempel ställa in en regel så att arbetstagare inte kan packa allokeringsrader som representerar försäljningsorder från olika kunder i samma behållare.

Så här ställer du in en behållarversionsmall:

1. Gå till **Warehouse management** \> **Inställningar** \> **Behållare** \> **Mall för behållarversion**.
1. Skapa en ny behållarversionsmall.
1. I fälten **Namn på skapande av behållare** och **Sekvensnummer**, ange namnet på mallen för skapande av behållare och den ordning som matchas med allokeringsrader.

    > [!NOTE]
    > Systemet använder den första mallen som allokeringsraden uppfyller frågekriterierna för. Sätt därför mallen med det mest specifika villkoret längst upp i listan. Ju bredare villkoren är, desto troligare är det att en allokeringsrad ska uppfylla kriterierna. Detta kan leda till att rader tilldelas fel container. Om det behövs kan du välja **Flytta upp** eller **Flytta ned** om du vill ändra mallsekvensen.

1. I fältet **behållargrupp-ID**, välj den behållargrupp som du vill skapa behållare från.
1. I fältet **Basfrågetyper**, välj den frågetyp som bestämmer vad som ska packas och vad filterfrågan ska baseras på i fältet . Följande alternativ är tillgängliga:

      - **Försäljningsallokeringsrad** - packa allokeringsrader som har skapats för försäljningsorder.
      - **Överför allokeringsrad** - packa allokeringsrader som har skapats för överföringsorder.
      - **Behållare** - Packa en behållare som redan har skapats av processen för skapande av behållare. Detta används till exempel för att kapsla containrar.

        > [!NOTE]
        > Om du vill använda kapslingsbehållare måste du göra metoden för skapande av behållare upprepningsbar. Mer information finns i [Påfyllnadsmallar](wave-templates.md).

1. På snabbfliken **Allmän** i fältet **Kod för påfyllnadssteg** anger du den unika identifieraren för påfyllnadsprocessen som länkar behållarversionsmallen till påfyllnadsmallen.
1. Markera kryssrutan **Tillåt delade plockningar** om du vill tillåta anställda att packa artiklar från en arbetsorder i separata behållare. Detta kräver att de hela kvantiteten ryms i containern. Den största måttenheten i allokeringsraden används alltid.
1. I fältet **Packa efter enhet** väljer du den måttenhet som ska representera behållaren. Du kan till exempel ange att ett ärende är en behållare. Om du packar efter måttenhet, kan du inte också ange en behållargrupp, eftersom måttenheten är behållaren.
1. Välj vilken förpackningsstrategi som ska användas i fältet **Strategi för packning av behållare**. Följande alternativ är tillgängliga:

    > [!NOTE]
    > Strategin gäller endast för säljallokeringsrader och allokeringsrader för överföring.

      - **Packa till alla öppna behållare** – Systemet utvärderar om allokeringsraden får plats i alla behållare som skapas.
      - **Packa endast till aktuell behållare** – Systemet utvärderar bara om allokeringsraden får plats i den senast skapade containern.

    Mer information och exempel som visar hur du arbetar med förpackningsstrategier för behållare finns i [Förpackningsstrategier för behållare](container-packing-strategy-overview.md).

1. Välj om du vill ställa in regler för packning av allokeringsrader i behållare **Avbrott för blandningslogik**. Du kan till exempel skapa en regel som låter arbetstagare packa allokeringsrader för två olika artiklar i samma behållare. Om du vill definiera en blandningsregel, följ dessa steg:

    1. På sidan **Avbrott för blandningslogik**, välj **Ny**.
    1. Välj det register som innehåller fälten som ska användas som ett villkor för det blandande logikavbrottet i fältet **Tabell**.
    1. Välj det fält som ska användas som ett villkor för det blandande logikavbrottet i fältet **Val av fält**.
    1. Upprepa de här stegen tills du har lagt till alla villkor för avbrottet för blandningslogik.

    > [!NOTE]
    > Om du använder blandningslogik, rekommenderar vi att du sorterar efter samma fält i frågan om filterkriterier. Detta minskar antalet behållare som skapas.
