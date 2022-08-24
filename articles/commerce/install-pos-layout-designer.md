---
title: Installera layoutdesignern för kassa
description: Du kan använda enklicksdesignern för att designa alternativa layouter för Modern POS (MPOS) och Cloud POS, i såväl liggande som stående läge, för butiker, register, kassörer och chefer.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 219684
ms.assetid: 2e2c4eea-c6e2-4912-9832-a6b22416e39f
ms.search.industry: Retail
ms.search.form: RetailTillLayout
ms.openlocfilehash: a610dbb9db63236ae7d182692f45f21c56982c69
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274270"
---
# <a name="install-the-pos-layout-designer"></a>Installera layoutdesignern för kassa

[!include [banner](includes/banner.md)]

Du kan använda enklicksdesignern för att designa alternativa layouter för Modern POS (MPOS) och Cloud POS, i såväl liggande som stående läge, för butiker, register, kassörer och chefer.

Det grafiska designgränssnittet för MPOS eller Cloud POS styrs av kassalådelayouten. En layout styr positionen för olika objekt. Du kan till exempel välja den totala layouten, layouten för artikelrutnät, kundlayout, betalningslayout samt layouten för olika menyknappar. Layouter innehåller det övergripande utseendet på det försäljningsgränssnitt som visas för arbetare.

## <a name="install-the-one-click-designer"></a>Installera enklicksdesignern

1. I Commerce använder du menyn i det övre vänstra hörnet för att navigera till **Butik och handel** &gt; **Kanalinställning** &gt; **Kassainställning** &gt; **Kassa** &gt; **Skärmlayouter**.
2. Välj en layout med ansökningstypen **Modern POS for Windows** eller **Cloud POS**, och klicka sedan på **layoutdesignern**.
3. På meddelandefältet som visas längst ner i Internet Explorer klicka på **Öppna** för att starta installationen av enklicksdesignern. (aviseringsfältet kan visas på en annan plats i andra webbläsare).
4. I meddelanderutan **Körning av program – Säkerhetsvarning** som visas klickar du på **Kör** för att installera värden för Retail designer. An förloppsindikator visar installationsförloppet.
5. När installationen är klar, på sidan **Logga in**, ange ditt handelsanvändarnamn och lösenord och klicka sedan på **Logga in** för att starta designer.
6. När dina inloggningsuppgifter har validerats och designverktyget startar, kan du utforma din egen layout eller ändra den befintliga.

    [![Layout i enklicksdesignern.](./media/screenlayoutdesign_mposdownload-1024x664.png)](./media/screenlayoutdesign_mposdownload.png)

## <a name="troubleshoot-the-installation-of-the-layout-designer"></a>Felsöka installationen av layoutdesignern

- När du klickar på **Designer** visas inte prompten att hämta (eller köra) installationsprogrammet, också tillåter inte dina aktuella säkerhetsinställningar att du hämtar filen. 

    **Lösningar:**

    - Kontrollera att blockering av popup-fönster avaktiveras för webbplatsen i Internet Explorer. Klicka på **Inställningar** &gt; **Alternativ** &gt; **Sekretess** &gt; **Hitta blockerare för popup-meddelanden** och ändra inställningen vid behov.
    - I Internet Explorer, lägg till Commerce URL till de tillförlitliga platserna. Klicka på **Inställningar** &gt; **Alternativ** &gt; **Säkerhet** &gt; **Säkra platser** &gt; **Platser** &gt; **Lägg till**.

- Programmet startar inte, och du uppmanas att kontakta leverantören.

    **Lösning:** I Internet Explorer, lägg till Commerce URL till de tillförlitliga platserna. Klick på **Inställning** &gt; **Alternativ** &gt; **Säkerhet** &gt; **Säkra platser** &gt; **Platser** &gt; **Lägg till**.

**Känt problem:** Designverktyget fungerar inte korrekt i webbläsarna Google Chrome och Mozilla Firefox. Vi arbetar på att åtgärda detta problem.

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera, installera och aktivera Retail Modern POS (MPOS)](retail-modern-pos-device-activation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
