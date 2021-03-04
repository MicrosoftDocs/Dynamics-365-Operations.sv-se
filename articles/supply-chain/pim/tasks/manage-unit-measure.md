---
title: Hantera måttenhet
description: I den här proceduren visas hur du definierar en måttenhet, anger översättningar för enheten och dess beskrivning och definierar konverteringsregler för relaterade enheter.
author: sorenva
manager: tfehr
ms.date: 07/08/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup, UnitOfMeasureCalculator, UnitOfMeasureWizard, UnitOfMeasureLookupTest
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d8d9b6f18fdc1c47d6a695ca6a2330f6f02fc1bd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437524"
---
# <a name="manage-unit-of-measure"></a>Hantera måttenhet

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du definierar en måttenhet, anger översättningar för enheten och dess beskrivning och definierar konverteringsregler för relaterade enheter. Du kan gå igenom den här proceduren med hjälp av demodata eller använda egna data.

1. Gå till **Navigeringsfönster > Moduler > Produktinformationshantering > Underhåll av frisläppt produkt**.
2. Klicka på **Enheter**.

## <a name="create-a-unit-of-measure"></a>Skapa en måttenhet
1. Klicka på **Ny**.
2. Fältet **Enhet** anger du ett värde. Ange ID eller symbolen som ska användas när du refererar till måttenheten.  
3. I fältet **Beskrivning** anger du ett värde. Ange ett beskrivande namn för måttenheten i systemspråket.  
4. Välj ett alternativ i fältet **Enhetsklass**. Enhetsklassen definierar vilken logisk gruppering, till exempel område, massa eller kvantitet som måttenheten ingår i.  
5. Ange ett nummer i fältet **Decimalprecision**. Ange antalet decimaler som den konverterade måttenheten måste avrundas till när en beräkning slutförs för måttenheten.  
6. Klicka på **Spara**.

## <a name="define-unit-translations"></a>Definiera enhetsöversättningar
1. Klicka på **Enhetstexter** i **åtgärdsfönstret**.
2. Klicka på **Ny**. Använd enhettext om du vill skapa en översättning av ID:t eller en symbol som representerar måttenheten för användning på externa dokument i kund - eller leverantörsspecifika språk.  
3. Ange eller välj ett värde i fältet **Språk**.
4. Skriv ett värde i fältet **Text**.
5. Klicka på **Spara**.
6. Stäng sidan.
7. Klicka på **Översatta enhetsbeskrivningar** i **åtgärdsfönstret**.
8. Klicka på **Ny**. Definiera språkspecifika beskrivningar för måttenheten.  
9. Ange eller välj ett värde i fältet **Språk**.
10. I fältet **Beskrivning** anger du ett värde.
11. Klicka på **Spara**.
12. Stäng sidan.

## <a name="define-unit-conversion-rules"></a>Definiera enhetskonverteringsregler
1. Klicka på **Enhetskonversationer** i **åtgärdsfönstret**. Definiera regler för att konvertera måttenheten till och från andra enheter i den valda enhetsklassen.  
2. Klicka på **Nytt** om du vill öppna dialogrutan.
3. Ange ett nummer i fältet **Faktor**. Konverteringsfaktor mellan Från enhet och Till enhet. Till exempel är konverteringsfaktorn från centimeter till meter 100, eftersom det går 100 centimeter på en meter.  
4. Ange eller välj ett värde i fältet **Till enhet**.
5. Markera ett alternativ i fältet **Avrundning**. Definiera hur det konverterade värdet ska avrundas.  
6. Klicka på **OK**.
7. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]