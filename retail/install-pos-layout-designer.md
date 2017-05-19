---
title: Installera layoutdesignern Retail POS
description: "Du kan använda enklicksdesignern för att designa alternativa layouter för Retail Modern POS (MPOS) och Cloud POS, i såväl liggande som stående läge, för butiker, register, kassörer och chefer."
author: MargoC
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: RetailTillLayout
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 219684
ms.assetid: 2e2c4eea-c6e2-4912-9832-a6b22416e39f
ms.search.region: Global
ms.search.industry: Retail
ms.author: athinesh
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: e60994f5c4fa38fc2be17b4021e2def904c87b7f
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="install-the-retail-pos-layout-designer"></a>Installera layoutdesignern Retail POS

[!include[banner](includes/banner.md)]


Du kan använda enklicksdesignern för att designa alternativa layouter för Retail Modern POS (MPOS) och Cloud POS, i såväl liggande som stående läge, för butiker, register, kassörer och chefer.

Det grafiska designgränssnittet för MPOS eller Cloud POS styrs av kassalådelayouten. En layout styr positionen för olika objekt. Du kan till exempel välja den totala layouten, layouten för artikelrutnät, kundlayout, betalningslayout samt layouten för olika menyknappar. Layouter innehåller det övergripande utseendet på det försäljningsgränssnitt som visas för arbetare.

## <a name="install-the-one-click-designer"></a>Installera enklicksdesignern
1.  I Microsoft Dynamics 365 for Operations använder du menyn i det övre vänstra hörnet för att navigera till **Butik** **och handel** &gt; **Kanalinställningar** &gt; **Kassainställningar** &gt; **POS** &gt; **Skärmlayout**.
2.  Välj en layout med ansökningstypen **Modern POS for Windows** eller **Cloud POS**, och klicka sedan på **Layout designer**.
3.  I meddelandefältet som visas längst ner i Internet Explorer-fönstret klickar du på **Open** att installera enklicksdesignern. (aviseringsfältet kan visas på en annan plats i andra webbläsare).
4.  I meddelanderutan **Körning av program - Säkerhetsvarning** som visas klickar du på **Kör**för att installera värden för Retail designer. An förloppsindikator visar installationsförloppet.
5.  När installationen har slutförts klickar du på sidan **Logga in**, anger ditt användarnamn och lösenord för Microsoft Dynamics 365 for Operations, och klickar sedan på **Logga in** för att starta designverktyget.
6.  När dina inloggningsuppgifter har validerats och designverktyget startar, kan du utforma din egen layout eller ändra den befintliga. [![Layout i enklicksdesignern](./media/screenlayoutdesign_mposdownload-1024x664.png)](./media/screenlayoutdesign_mposdownload.png)

## <a name="troubleshoot-the-installation-of-the-layout-designer"></a>Felsöka installationen av layoutdesignern
-   När du klickar på **Designer**visas inte prompten att hämta (eller köra) installationsprogrammet, också tillåter inte dina aktuella säkerhetsinställningar att du hämtar filen. **Lösningar:**
    -   Kontrollera att blockering av popup-fönster avaktiveras för webbplatsen i Internet Explorer. Klicka på **Inställningar** &gt; **Alternativ** &gt; **Sekretess** &gt; **Hitta blockerare för popup-meddelanden** och ändra inställningen vid behov.
    -   Lägg till webbadressen (URL) för Dynamics 365 for Operations URL till dina betrodda webbplatser i Internet Explorer. Klicka på **Inställningar** &gt; **Alternativ** &gt; **Säkerhet** &gt; **Säkra platser** &gt; **Platser** &gt; **Lägg till**.
-   Programmet startar inte, och du uppmanas att kontakta leverantören. **Lösning:** Lägg till webbadressen (URL) för Dynamics 365 for Operations till dina betrodda webbplatser i Internet Explorer. Klick på **Inställning** &gt; **Alternativ** &gt; **Säkerhet** &gt; **Säkra platser** &gt; **Platser** &gt; **Lägg till**.

**Känt problem:** Designverktyget fungerar inte korrekt i webbläsarna Google Chrome och Mozilla Firefox. Vi arbetar på att åtgärda detta problem.

<a name="see-also"></a>Se även
--------

[Konfigurera, hämta, installera och aktivera Retail Modern POS](retail-modern-pos-device-activation.md)




