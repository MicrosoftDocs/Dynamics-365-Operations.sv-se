---
title: Definiera skapande av behållare
description: I den här avsnittet beskriver hur du automatiserar skapandet av behållare för last Lagerstyrning.
author: ShylaThompson
manager: tfehr
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable, WHSContainerizatonHistory, WHSContainerPackingPolicyChange, WHSManifestShipmentContainers, WHSAllowedContainerTypeGroup, WHSPostMethod, WHSContainerCreateDialog, WHSContainerCloseDiag, WHSContainer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0f28be8993d5fc0a1632cf7a534808e64980c09b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977048"
---
# <a name="set-up-containerization"></a>Definiera skapande av behållare

[!include [banner](../../includes/banner.md)]

I den här avsnittet beskriver hur du automatiserar skapandet av behållare för last Lagerstyrning. Automatiskt skapande av behållare skapar behållare och plockarbetet för leveranser när en påfyllnad bearbetas och arbetsrader kan delas i kvantiteter som passar behållarna. Detta hjälper lagerarbetare att plocka artiklarna direkt till den valda behållaren. Jämfört med den manuella förpackningsprocessen automatiseras uppgifter som till exempel att skapa behållare, tilldela artiklar och stänga behållare av systemet. I den här proceduren används USMF-demonstrationsföretaget och utförs av en lagerchef.


## <a name="set-up-a-wave-template"></a>Ställa in en påfyllnadsmall
1. I navigeringsfönstret, gå till **moduler > lagerstyrning > inställningar > påfyllnader > påfyllnadsmallar**.
2. Välj **Ny**.
3. I fältet **Påfyllnadsmallnamn**, skriv ett värde.
4. Skriv ett värde i fältet **Beskrivning av påfyllnadsmall**.
5. i fältet **Plats** anger eller väljer du ett värde.
6. Ange eller välj ett värde i fältet **Lagerställe**.
7. Visa avsnittet **Metoder**. Fönstret **Valda metoder** visar metoderna för den valda påfyllnadsmallstypen. Påfyllnadsmallen måste inkludera metoden för skapande av behållare.  
8. I fältet **Kod för påfyllnadssteg**, skriv ett värde. Ange en Kod för påfyllnadssteg för den tillagda metoden, som kan vara en kod. Det går att lägga till metod mer än en gång och tilldela olika koder för påfyllnadssteg. Om du vill göra detta väljer du **Kan upprepas för den här metoden** på sidan **Metoder för bearbetning av påfyllnad**.  
9. Välj **Spara**.
10. Stäng sidan.

## <a name="set-up-a-container-type"></a>Ställ in en behållartyp
1. I navigeringsfönstret, gå till **moduler > lagerstyrning > inställningar > behållare > behållartyper**. Du kan definiera dina behållare på sidan **Behållartyper**. Du kan konfigurera de fysiska dimensionerna på behållare, inklusive taravikt, högsta vikt, högsta volym, längd, bredd, vikt och höjd. I det här exemplet har vi tre olika storlek på boxar.  
2. Välj **Ny**.
3. Ange ett värde i fältet **Behållartypkod**.
4. Ange ett nummer i fältet **Taravikt**.
5. Ange ett värde i fältet **Högsta vikt**.
6. Välj ett nummer i fältet **Volym**.
7. I fältet **Längd**, ange ett tal.
8. Ange ett värde i fältet **Bredd**.
9. Ange ett värde i fältet **Höjd**.
10. I fältet **Beskrivning** anger du ett värde.
11. Välj **Spara**.
13. Upprepa steg 2-11 ytterligare två gånger för att göra tre totala behållartyper.
14. Stäng sidan.

## <a name="set-up-a-container-group"></a>Ställ in en behållargrupp
1. I navigeringsfönstret, gå till **moduler > lagerstyrning > inställningar > behållare > behållargrupper**.
2. Klicka på **Ny** i åtgärdsfönstret. Du kan ställa in logiska grupper av behållartyper. För varje grupp kan du ange sekvens för packning av containrar och procentsatsen av containrarna som ska fyllas. I används storleksdimensioner för artikeln för att avgöra om den passar i en behållare. Den behållare som är närmast artikelns storlek används. Om du har flera behållartyper i en grupp, rekommenderar vi att sekvensen ordnas efter storlek, så att den största, är den första nummer 1 i sekvensen, och den mest minsta behållaren är den sista.    
3. I fältet **Behållargrupp-ID** anger du ett värde du skapade tidigare.
4. I fältet **Beskrivning** anger du ett värde.
5. Upprepa steg 2-4 för alla tre behållartyper som du skapade tidigare.
6. Välj **Spara**.
7. Stäng sidan.

## <a name="set-up-a-container-build-template"></a>Ställa in en behållarversionsmall
1. I navigeringsfönstret, gå till **moduler > lagerstyrning > inställningar > behållare > uppbyggnadsmallar för behållare**.
2. Välj **Ny**. Behållareversionmallen baseras på vilket process för skapande av fraktbehållare som utförs. Varje behållareversionmall definierar en process för skapande av fraktbehållare som ska användas i en påfyllnadsmall. Alternativet **Redigera fråga** låter dig definiera de villkor som den valda mallen ska bearbeta. Till exempel vill du kanske bara att köra skapande av fraktbehållare för specifika kunder, produkter, eller lagerställen och du kan lägga till motsvarande frågeintervall i mallen. Fältet **Kod för påfyllnadssteg** är hur en behållarversionsmall länkas till steg i en påfyllnadsmall. När en påfyllnad körs, bestämmer den vilka/vilken behållarversionsmall(ar) som används för att initiera skapande av fraktbehållare. Fältet Basfrågetyper bestämmer vad som ska packas och vad filterfrågan ska baseras på. 
3. Skriv ett värde i fältet **Behållarmall-ID**.
4. I fältet **Behållargrupp** kan du ange eller välja ett värde.
5. I fältet **Kod för påfyllnadssteg**, skriv ett värde.
6. Markera kryssrutan **Tillåt delade plockningar**.
7. Välj **Spara**.
8. Klicka på **Blandade begränsningar för behållare**. Avbrott för blandningslogik låter dig ställa in regler för att packa allokeringsrader i behållare. Om du t.ex. lägger till fältet **Artikelnummer**, när artiklar tilldelas till behållare, kommer en ny behållare att skapas om det finns ett nytt artikelnummer. Detta kommer att förebygga att arbetare packar allokeringsrader för två olika kunder i samma behållare.  
9. Välj **Ny**.
10. Markera ett alternativ i fältet **Tabell**.
11. Ange eller välj ett värde i fältet **Välj**.
12. Välj **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]