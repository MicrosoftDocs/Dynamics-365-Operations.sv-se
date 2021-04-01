---
title: Ställ in och designa inleveransformat
description: Den här artikeln beskriver hur du ändrar formulärlayouter om du vill styra hur kvitton, fakturor och andra dokument skrivs ut. Dynamics 365 Commerce inkludera finns en layoutdesigner för formulär som du kan använda för att enkelt skapa och ändra olika typer av formulärlayouter.
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFormLayout
audience: Application User
ms.reviewer: josaw
ms.custom: 57841
ms.assetid: e530dd8e-95e2-4021-90bd-ce1235f9e250
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: c44798c6b879ebd95618d976beebe1d41b40dcdd
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243755"
---
# <a name="set-up-and-design-receipt-formats"></a>Ställ in och designa inleveransformat

[!include [banner](includes/banner.md)]

Den här artikeln beskriver hur du ändrar formulärlayouter om du vill styra hur kvitton, fakturor och andra dokument skrivs ut. Dynamics 365 Commerce finns en layoutdesigner för formulär som du kan använda för att enkelt skapa och ändra olika typer av formulärlayouter.

> [!IMPORTANT]
> Du måste ställa in formulärlayouter och kvittoprofiler om du vill skriva ut kvitton och andra dokument från Retail Modern POS och Cloud POS. Du kan inkludera flera formulärlayouter i en kvittoprofil. Du kan sedan tilldela mottagandet profil till en skrivare genom att modifiera hårdvara profil.

## <a name="set-up-a-receipt-format"></a>Ställa in en kvittoformat

1. Klicka på **butiker och handel** &gt; **kanalinställning** &gt; **kassainställningar** &gt; **kassa** &gt; **kvittoformat**.
2. På **kvittot format** sida, klicka på **Ny för** att skapa en ny form layout, eller välja en befintlig form layout.
3. I **mottagandet format** anger du ett id för blankettlayout, och välj sedan den typ av inleverans som denna layout används för. Du kan även ange en beskrivning och ett kortnamn för mottagande i **fältet Titel** .
4. På den **allmänna** snabbfliken, välj ett alternativ för att ange utskriftsinställningarna:

    - **Skriv alltid ut** – Kvittot skrivs ut automatiskt.
    - **Skriv inte ut** – mottagandet inte skrivas ut.
    - **Fråga användaren** – uppmanas användaren att skriva ut kvittot.
    - **Vid behov** – Detta alternativ används endast för gift kvitton. När det här alternativet är markerat, kan användaren skriva ut en gåva mottagandet från **ändra** sida, om en gåva inleverans krävs.

## <a name="print-images"></a>Skriv ut bilder

Kvittodesignern innehåller en **Logotyp**-variabel som kan användas för att ange vilka bilder som ska skrivas ut på kvittot. Bilder som ingår i kvitton med hjälp av variabeln **Logotyp** ska vara monkroma bitmappsfiltyper (.bmp). Om en .bmp-bild anges i kvittodesignern men inte skrivs ut när den skickas till skrivaren, kan detta bero på att filstorleken är för stor eller på att bilddimensionerna inte är kompatibla med skrivaren. Försök att reducera bildfilslösningen om detta inträffar.   

## <a name="design-a-receipt-format"></a>Designa ett kvittoformat

Använd den grafiska layoutdesignern för att grafiskt skapa layouten för formulärdokumentet. **Mottagandeformatdesigner** sidan har tre sektioner: **Sidhuvud**, **Rader** och **Sidhuvud**. Vissa typer av blankettlayouter använder element från alla tre delar, medan andra typer använder element från endast en eller två delar. Visa element som är tillgängliga för varje avsnitt, klicka på lämplig knapp i navigeringsfältet till vänster på sidan.

1. Klicka på **butiker och handel** &gt; **kanalinställning** &gt; **kassainställningar** &gt; **kassa** &gt; **kvittoformat**.
2. På **kvittot format** väljer du en form layout och klicka sedan **Designer**.
3. Klicka på **Kör** för att starta installationen av handel designer värd.
4. Om anmälan bar som visas längst ner i Internet Explorer klicka på **Öppna** att starta installationen av etta-klickar designer. (Meddelandefältet kan visas på en annan plats i andra webbläsare.) Förloppsindikatorn visar förloppet för installationen.
5. När installationen är klar, skriv ditt handel användarnamn och lösenord och klicka sedan på **Logga in** för att starta designer.
6. Efter dina inloggningsuppgifter är validerade och designern börjar, du kan börja utforma mottagandet format eller ändra ett befintligt format.
7. För att skapa delar av formuläret, välj **sidhuvud**, **linjerna**, eller **sidfotssektion** och sedan dra ett element från den delen av arbetsytan. De flesta element innehåller variabler som fylls automatiskt med data från databasen. Andra element, till exempel **Text**, kan du skriva ut egen text på kvittot.

    > [!NOTE]
    > Du kan ange hur många rader varje sektion täcker genom att justera siffran i det nedre högra hörnet i det avsnittet. För att göra det enklare att modifiera ett avsnitt, öka dess höjd genom att dra den dimensionering bar längst ner. Höjden på sektion på arbetsytan inte påverkar antalet rader på det faktiska mottagandet.

8. När du drar ett element till arbetsytan, ange egenskaper för artikeln i fönstret **Objektinformation** längst ner på sidan. Ange ett eller fler av följande inställningar:

    - **Anpassa** – ställ in justeringen för fältet till **Vänster** eller **Höger**.
    - **Fyll char** – Ange det vita utrymmet karaktär. Som standard används ett tomt utrymme, men du kan ange vilket tecken som helst.
    - **Prefix** – Ange det värde som visas i början av fältet. Den här inställningen gäller endast de **rader** i layouten.
    - **Tecken** – Ange det maximala antalet tecken som kan innehålla om elementet innehåller en variabel. Om texten i fältet är längre än antalet tecken som du anger, trunkeras texten för att passa fältet.
    - **Variabel** – Den här kryssrutan markeras automatiskt om elementet innehåller en variabel och kan inte anpassas.
    - **Teckenstil** – Ange teckenstil till antingen **Normal** eller **Fet**. Fetstil använd dubbelt gånger så mycket utrymme som vanliga bokstäver. Därför kan vissa tecken kan vara trunkerad.
    - **Teckenstorlek** – Ange teckenstorlek till antingen **Normal** eller **Stor**. Stora bokstäver är dubbelt så höga som vanliga bokstäver. Därför kan använda stora bokstäver medföra överlappande text i inleveransen.
    - **Ta bort** – klicka på den här knappen om du vill ta bort den markerade delen från formulärlayouten.

## <a name="assign-receipt-profiles"></a>Tilldela mottagandet profiler

Mottagandet profiler tilldelas direkt till skrivare via hårdvara profil.

1. Öppna hårdvara profil genom att klicka på **Butik och handel** &gt; **Kanalinställning** &gt; **Kassainställning** &gt; **Kassaprofiler** &gt; **Hårdvaruprofil**.
2. Välj skrivaren och sedan, i **mottagandet profil** fält, tilldela mottagandet profil för användning i registret.

> [!NOTE]
> Om två skrivare används en skrivare kan användas för att skriva ut 40-kolumnen termiska kvitton. Den andra skrivare används vanligen för att skriva ut sida typerna som kräver mer information. Dessa inleveranstyperna inkludera kundens inköpsorder och kundfakturor.


[!INCLUDE[footer-include](../includes/footer-banner.md)]