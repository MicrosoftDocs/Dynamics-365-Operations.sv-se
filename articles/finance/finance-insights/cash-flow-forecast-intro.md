---
title: Kassaflödesprognos (förhandsversion)
description: I det här avsnittet beskrivs funktionen för kassaflödesprognos.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-19
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 64935db3b50e7598f2076ecbec72aba020d4f908
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186550"
---
# <a name="cash-flow-forecast-preview"></a>Kassaflödesprognos (förhandsversion)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Kassaflödet är kritiskt för alla företag. Till och med lönsamma företag kan bli insolventa om de inte upprätthåller kassaflödet för att uppfylla omedelbara behov. Prognosfunktionerna för kassaflöde i Finance-insikter gör det enklare för företag att övervaka och hantera sina kontantsaldon effektivt. Funktionen använder maskininlärning för att hjälpa företag prognostisera kassaflöden mer noggrant än tidigare. Den kan också hjälpa chefer att fatta beslut som optimerar affärsmöjligheter i samband med deras aktuella kassaposition. 

För de flesta företag, är hantering av kassaflöde och körning av kassaflödesprognoser är en omständlig, repetitiv och manuell process. De flesta företag använder Microsoft Excel-lösningar med varierande grad av komplexitet. Utmaningarna med att korrekt prognostisera kassaflödet är bland andra:

- Data är inte tillgängliga för beslutsfattarna eftersom de är spridda på flera ställen, bland annat: 
  - Redovisnings- eller planeringssystem för företagsresurser
  - Programvara för ekonomisk planering
  - Excel
  - Ytterligare programvarutillämpningar 
- Prognoser baseras på interna kunskaper som finns i "silor" inom varje domän eller avdelning.
- Att mäta noggrannheten i kassaflödesprognoser när ekonomin har realiserats är osäkert och svårt.
    
## <a name="details-of-the-cash-flow-forecasts-capability"></a>Information om funktionen för kassaflödesprognoser
Funktionen Kassaflödesprognoser omfattar följande funktioner: 

- Gör det enkelt att integrera kassaflödesdata från externa system till Dynamics 365 Finance. Kassaflödesprognoser kan också använda ramverket för import-export av data. Detta ramverk gör det enkelt att integrera med Excel OData. Du kan också kombinera data från flera källor för att skapa en omfattande kassaflödeslösning. 

- Introducerar intelligent kassaposition. Kassapositionen skapas utifrån kundens betalningsbeteende för att förutsäga när ett företag kan förvänta sig kontanter att anlända till sina konton. Den analyserar också historiska mönster för att betala leverantörer, för att förutsäga när framtida fakturor och order sannolikt ska betalas. 

- Introducerar intelligenta kassaflödesprognoser för långsiktiga prognoser, med hjälp av tidsserieprognoser via automatisk integrering med AI Builder.

- Ger möjlighet att spara specifika kassaflödespositioner och prognoser, redigera dem och sedan enkelt jämföra och mäta prognosresultatet med den faktiska ekonomin.

- Möjliggör konsekvensanalys via jämförelser av ögonblicksbilder. Du kan till exempel skapa flera ögonblicksbilder som representerar optimistiska, pessimistiska och mest realistiska vyer av ditt kassaflöde och sedan jämföra och visa skillnaderna.

- Ger möjlighet att visa kassaflödesprognosen i flera valutor, för juridiska personer och filtrera och visa kassaflöden som hör till ett bankkonto. 

- Gör att du kan filtrera och visa bankkonton som hör till ekonomiska dimensioner.

Med funktionen för kassaflödesprognos i Dynamics 365 Finance kan din organisation omvandla omständliga, komplexa och repetitiva kassaflödesprognoser till en enkel, automatiserad process. Genom att automatisera de mest omständliga aspekterna av kassaflödesprognoser kan du fokusera på de viktiga beslut som behövs för att driva fram önskade affärsresultat.

## <a name="setting-up-dimensions-for-cash-flow-forecasting"></a>Konfigurera dimensioner för kassaflödesprognoser
Med en ny flik på sidan **Konfiguration av kassaflödesprognos** kan du kontrollera vilka ekonomiska dimensioner som ska användas för filtreringen i arbetsytan **Kassaflödesprognoser**. Den här fliken visas endast om funktionen Kassaflödesprognoser är aktiverad. 

På fliken **Dimensioner** väljer du i listan med dimensioner som ska användas för filtrering och flyttar dem till den högra kolumnen med piltangenterna. Endast två dimensioner kan väljas för filtrering av kassaflödesprognosdata. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
