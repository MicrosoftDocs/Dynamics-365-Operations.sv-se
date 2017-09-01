--- 
title: "Hantera måttenhet"
description: "I den här proceduren visas hur du definierar en måttenhet, anger översättningar för enheten och dess beskrivning och definierar konverteringsregler för relaterade enheter."
author: sorenva
manager: AnnBe
ms.date: 02/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: de5baa1e5c30ee998d113f7366c445a65723dfdc
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="manage-unit-of-measure"></a>Hantera måttenhet

[!include[task guide banner](../../includes/task-guide-banner.md)]

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

