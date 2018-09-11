--- 
title: "Hantera måttenhet"
description: "I den här proceduren visas hur du definierar en måttenhet, anger översättningar för enheten och dess beskrivning och definierar konverteringsregler för relaterade enheter."
author: sorenva
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6bb7a5133e9412f4ed6fb74f0d3ee595c07a0c4b
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="manage-unit-of-measure"></a>Hantera måttenhet

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du definierar en måttenhet, anger översättningar för enheten och dess beskrivning och definierar konverteringsregler för relaterade enheter. Du kan gå igenom den här proceduren med hjälp av demodata eller använda egna data.

1. Gå till Underhåll av frisläppt produkt.
2. Klicka på Enheter.

## <a name="create-a-unit-of-measure"></a>Skapa en måttenhet
1. Klicka på Ny.
2. Skriv ett värde i fältet Enhet.
    * Ange ID eller symbolen som ska användas när du refererar till måttenheten.  
3. Ange ett värde i fältet Beskrivning.
    * Ange ett beskrivande namn för måttenheten i systemspråket.  
4. Välj ett alternativ i fältet Enhetsklass.
    * Enhetsklassen definierar vilken logisk gruppering, till exempel område, massa eller kvantitet som måttenheten ingår i.  
5. Ange ett nummer i fältet Decimalprecision.
    * Ange antalet decimaler som den konverterade måttenheten måste avrundas till när en beräkning slutförs för måttenheten.  
6. Klicka på Spara.

## <a name="define-unit-translations"></a>Definiera enhetsöversättningar
1. Klicka på Enhetstexter.
2. Klicka på Ny.
    * Använd enhettext om du vill skapa en översättning av ID:t eller en symbol som representerar måttenheten för användning på externa dokument i kund - eller leverantörsspecifika språk.  
3. Ange eller välj ett värde i fältet Språk.
4. Skriv ett värde i fältet Text.
5. Klicka på Spara.
6. Stäng sidan.
7. Klicka på Översatta enhetsbeskrivningar.
8. Klicka på Ny.
    * Definiera språkspecifika beskrivningar för måttenheten.  
9. Ange eller välj ett värde i fältet Språk.
10. Ange ett värde i fältet Beskrivning.
11. Klicka på Spara.
12. Stäng sidan.

## <a name="define-unit-conversion-rules"></a>Definiera enhetskonverteringsregler
1. Klicka på Enhetskonverteringar.
    * Definiera regler för att konvertera måttenheten till och från andra enheter i den valda enhetsklassen.  
2. Klicka på Nytt om du vill öppna dialogrutan.
3. Ange ett nummer i fältet Faktor.
    * Konverteringsfaktor mellan Från enhet och Till enhet. Till exempel är konverteringsfaktorn från centimeter till meter 100, eftersom det går 100 centimeter på en meter.  
4. Ange eller välj ett värde i fältet Till enhet.
5. Markera ett alternativ i fältet Avrundning.
    * Definiera hur det konverterade värdet ska avrundas.  
6. Klicka på OK.
7. Stäng sidan.


