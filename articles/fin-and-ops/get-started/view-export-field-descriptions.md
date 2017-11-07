---
title: "Visa och exportera fältbeskrivningar"
description: "Den här artikeln innehåller en beskrivning av hur du visar fältbeskrivningar och hur du använder sidan Fältbeskrivningar vid export av beskrivningar."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FieldDescriptions
audience: Application User, Developer, IT Pro
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 11534
ms.assetid: e2795f51-a8a7-4c74-bdb9-b1be93bdd358
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 908f854e5ca50f4298110c08c87fefd9427b5cc9
ms.openlocfilehash: 841c18630a59c3f5a7b51cd005962fa8a7f7163f
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="view-and-export-field-descriptions"></a>Visa och exportera fältbeskrivningar

[!include[banner](../includes/banner.md)]


Den här artikeln innehåller en beskrivning av hur du visar fältbeskrivningar och hur du använder sidan Fältbeskrivningar vid export av beskrivningar.

Microsoft Dynamics 365 for Finance and Operations har beskrivningar för vissa av de mer komplexa fälten. Dessa beskrivningar visas när du håller muspekaren över ett fält. På sidan **Fältbeskrivningar** kan du visa och exportera fältbeskrivningar. 

Inte alla sidor har fältbeskrivningar. Vi tillhandahåller enbart beskrivningar av de mer komplexa fälten och inte av dem där användningen av fältet är tydligt. Av den anledningen saknas fältbeskrivningar på vissa sidor. Andra sidor innehåller några få beskrivningar och några av de mer komplexa sidorna, till exempel många av parametersidorna, har många beskrivningar. 

Om du har tillgång till utvecklingsmiljön för Finance and Operationskan kan du lägga till egna fältbeskrivningar och anpassa befintliga beskrivningar. Du kan till exempel lägga till företagsspecifik information i en fältbeskrivning. Mer information hittar du i [Hjälp för Anpassa fält](../../dev-itpro/user-interface/customize-field-help.md).

## <a name="see-field-descriptions-in-the-user-interface"></a>Se fältbeskrivningarna i användargränssnittet.
Du kan visa fältbeskrivningar genom att hovra över ett fält. Om det inte finns någon beskrivning ser du fältnamnet när du för muspekaren över fältet. (Obs! I Dynamics AX 7.0 (February 2016) kan fältbeskrivningarna endast visas på sidan **Fältbeskrivningar**.) Följande illustration visar den fältbeskrivning som visas när du för muspekaren över fältet **Lås artiklar under inventeringen**. 

[![Exempel på en fältbeskrivning](./media/field-description.png)](./media/field-description.png)

## <a name="use-the-field-descriptions-page-to-view-and-export-field-help"></a>Använd sidan Fältbeskrivningar för att visa och exportera hjälp för fält.
På sidan **Fältbeskrivningar** kan du visa och exportera fältbeskrivningar. Du kan se de beskrivningar som är tillgängliga en sida i taget.

### <a name="view-the-descriptions-for-a-page"></a>Visa beskrivningarna för en sida

Visa beskrivningarna för en sida genom att följa det här steget:

-   Ange sidan namn i fältet **Välj en sida**. Du kan också klicka på pilen om du vill öppna en lista över alla sidor och sedan bläddra i eller filtrera listan.

Du kan antingen använda sidans namn som visas i användargränssnittet (UI) (till exempel **Kunder**) eller kodnamnet (AOT-namn) som visas när du högerklickar på en sida (till exempel **CustTable**). 

Information om olika sätt att filtrera listan över sidor hittar du i avsnittet "Söka efter en sida" senare i den här artikeln. 

Om du ställer in alternativet **Inkludera fält utan en beskrivning** till **Ja** kommer alla fält på sidan att visas, oavsett om de har en fältbeskrivning eller inte.

### <a name="export-the-descriptions-for-a-page"></a>Exportera beskrivningarna för en sida

Om du vill exportera beskrivningarna för en sida ska du följa de här stegen:

1.  Välj en sida i fältet **Välj en sida**.
2.  Klicka på knappen **Öppna i Microsoft Office** i det övre högra hörnet och klicka sedan på **FieldDescriptionTmp**.

### <a name="searching-for-a-page"></a>Söka efter en sida

Det finns flera sätt att söka efter en sida i fältet **Välj en sida**. I många fall måste du klicka på pilen i fältet **Välj en sida** om du vill öppna listrutan och sedan välja från en filtrerad lista över sidor.

-   Skriv in en del av namnet och öppna sedan listrutan för att välja från en filtrerad lista över sidor.
-   Öppna listrutan och klicka antingen på rubriken **Sök namn** högst upp i listan eller på rubriken **Sök AOT-namn**. Efter detta öppnas en dialogruta där du kan använda avancerada filtreringsalternativ såsom **Sidnamn som börjar med**.
-   Skriv in hela namnet på sidan. När du använder det här alternativet är det bäst att öppna listrutan och se vad mer som finns i listan, även om fältbeskrivningar visas.
    -   Om det finns en enskild exakt matchning på namnet visas fältbeskrivningarna för den sidan.
    -   Om det finns fler än en exakt matchning visas inga beskrivningar. Du måste öppna listrutan och välja sida.
    -   Om namnet du angav är en del av namnet på en annan sida ser du beskrivningarna av sidan. Om du öppnar listrutan kan du se ytterligare sidor som innehåller det aktuella namnet.

Inga beskrivningar visas om du exempelvis skriver **Inventering** i fältet ****Välj en sida****. Om du öppnar listrutan och ser du att det finns två sidor med namnet **Inventering** och flera sidor som innehåller ordet "Inventering". Om du väljer sidan med AOT-namnet **InventJournalCount** visas fältbeskrivningarna för den sidan. Om du öppnar listrutan igen ser du att listan nu innehåller alla sidor som har "InventJournalCount" som en del i AOT-sidans namn.

## <a name="troubleshooting"></a>Felsökning
Det här avsnittet innehåller information som hjälper dig att felsöka problem som kan uppstå när du använder fältbeskrivningar.

### <a name="i-cant-find-a-field-description"></a>Jag kan inte hitta en fältbeskrivning

Vi håller på att lägga till beskrivningar av de mer komplexa fälten. Om du behöver hjälp med ett visst fält kan du kontakta oss genom att lägga till en kommentar i det här avsnittet.

### <a name="the-field-description-isnt-helpful"></a>Fältbeskrivningen är inte till någon hjälp

Kontakta oss genom att lägga till en kommentar i det här avsnittet. Beskriv gärna vilken ytterligare information du behöver.

### <a name="i-cant-find-a-field-on-the-field-descriptions-page"></a>Jag kan inte hitta ett fält på sidan Fältbeskrivningar.

Ställ in alternativet **Inkludera fält utan en beskrivning** på **Ja** om du vill visa alla fälten på en sida. Klicka på fältet **Välj en sida** för att kontrollera att du har markerat rätt sida. Om namnet du angav är en del av ett annat fältnamn kanske du har markerat en sida med ett längre namn.

### <a name="i-cant-find-a-page-on-the-field-descriptions-page"></a>Jag kan inte hitta en sida på sidan Fältbeskrivningar.

Information om olika sätt att hitta sidor hittar du i avsnittet "Söka efter sidor" tidigare i den här artikeln. Om du har skrivit in sidans exakta namn kan det hända att fältbeskrivningarna inte visas om det finns fler än en sida med samma namn. Klicka på pilen i fältet **Välj en sida** om du vill öppna en filtrerad lista över de sidor som är tillgängliga.

<a name="see-also"></a>Se även
--------

[Hjälp för Anpassa fält](../../dev-itpro/user-interface/customize-field-help.md)





