---
title: Påfyllnadsmetoder och kvantitetsändring
description: Det här ämnet innehåller information om påfyllnadsmetoder i Planeringsoptimering. Det förklarar också hur flera orderkvantitet för en produkt påverkar resultatet.
author: t-benebo
ms.date: 6/1/2021
ms.topic: article
ms.search.form: ReqGroup, ReqItemTable, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fc7eb00f62b334ba032af6fef87c243a7ba0835a
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2022
ms.locfileid: "8468550"
---
# <a name="replenishment-methods-and-quantity-modification"></a>Påfyllnadsmetoder och kvantitetsändring

[!include [banner](../../includes/banner.md)]

Det här ämnet innehåller information om påfyllnadsmetoder i Planeringsoptimering. Det förklarar också hur flera orderkvantitet för en produkt påverkar resultatet.

Påfyllnadsmetoder kallas också för disponeringsmetoder och partistorleksmetoder.

## <a name="coverage-codes"></a>Täckningskoder

Planeringsoptimering kan konfigureras till att använda olika återanskaffningsmetoder. Påfyllnadsmetoderna är de tekniker som systemet använder för att beräkna behoven för en produkt. Påfyllnadsmetoder definieras per disponeringskoder som du kan ställa in för disponeringsgruppen eller produkten.

Följande disponeringskoder kan användas vid planeringsoptimering:

- **Period** - den påfyllnadsmetod som kombinerar hela efter frågan för en period till en order för produkt. Ordern planeras under den första dagen i perioden och dess kvantitet uppfyller nettokraven under den fastställda perioden. Perioden inleds med det första efter frågan av produkten och täcker den definierade tiden i tid. Nästa period kommer att inledas med nästa behov av produkten. Disponeringskod *Period* används ofta för icke-förutsägbar inventering, säsongspåverkade produkter eller högkostnadsprodukter. Illustrationen nedan visar ett exempel.

    ![Exempel på kodanvändning för av Perioddisponering.](./media/coverage-code-period.png "Exempel på användning av period disponeringskod")

- **Krav** - I påfyllnadsmetod i vilken systemet skapar en planerad inköps-, överförings- eller produktionsorder per behov för artikeln. Denna metod används för höga produkter som har återkommande efterfrågan. Disponeringskod *Krav* används ofta för konfigurerbara produkter eller scenarier som måste beställas. Illustrationen nedan visar ett exempel.

    ![Exempel på kodanvändning för kravdisponering.](./media/coverage-code-requirement.png "Exempel på användning av krav disponeringskod")

- **Min./Max.** – Påfyllnadsmetoden baseras på lagernivån. Den definierar påfyllnaden av lagret upp till en specifik nivå när den prognosterade lagerbehållningsnivån är under ett specifikt tröskelvärde. Kvantiteten för påfyllnaden är differensen mellan den högsta nivån och den förutsagda behållningsnivån. *Minsta/högsta.* disponeringskod används ofta för förutsägbar inventering, höga kostnader eller billigaste produkter. Illustrationen nedan visar ett exempel.

    ![Exempel på användning av min/max-disponeringskod.](./media/coverage-code-min-max.png "Exempel på användning av min/max disponeringskod")

- **Manuell** - Påfyllnadsmetoden för partistorlek där systemet inte föreslår inköps-, överförings- eller tillverkningsorder för produkten. I stället ansvarar planeraren för produkten för att skapa de order som krävs för påfyllnaden av produkten. *Manuell* disponeringskod används ofta för produkter som systemgenererade planerade order inte är önskade för.

## <a name="impact-of-the-order-quantity-from-default-order-settings"></a>Inverkan från standardorderinställningarna för orderkvantiteten

På sidan **inställning för standardorder** för en frisläppt produkt kan du ange följande kvantitetsinställningar på snabbflikarna **Inköpsorder**, **Lager** och **Försäljningsorder**. (Snabbfliken **Lager** används för både överföringsorder och tillverkningsorder.)

- **Flera** – Planerade order kommer att vara en multipel av den här kvantiteten.

    Till exempel om fältet **Flera** anges till *5*, kan en order vara för kvantiteten 5, 10, 15, 20 och så vidare.

- **Minsta orderkvantitet** – Planerade order understiger inte det angivna värdet.

    Om till exempel fältet **Minsta orderkvantitet** är inställt på *10*, skapas en planerad order med kvantiteten 10, även om det bara krävs fyra för att uppfylla efterfrågan.

- **Högsta orderkvantitet** – Planerade order överstiger inte det angivna värdet. Om efterfrågan är större än värdet **Maximal orderkvantitet** skapas flera planerade order för att täcka den.

    Om till exempel fältet **Max. orderkvantitet** är inställt på *100* och efterfrågan är 450, skapas fyra planerade order för kvantiteten 100 och en planerad order för kvantiteten 50.

## <a name="examples-of-replenishment-that-use-the-minmax-coverage-code"></a>Exempel på påfyllnad där min./max används. disponeringskod

Om du inte anger ett värde i fältet **Flera** för en produkt på sidan **inställning för standardorder**, och om du använder *Min./Max.* påfyllnadsmetod kommer Planeringsoptimering fylla på lagret till en specifik nivå när den prognostiserade lagerbehållningsnivån är under ett specifikt tröskelvärde.

Om du definierar en multipelkvantitet för en produkt måste du ange *Min./Max.* påfyllnadsmetoden ändrar dess beteende och tar hänsyn till värdet **flera**.

Med andra ord fyller Planeringsoptimering fortfarande på lagret upp till den definierade maximinivån när den förutsagda behållningsnivån är mindre än den definierade miniminivån. Påfyllnadskvantiteten måste dock vara en multipel av värdet **Flera**.

Om påfyllnadskvantiteten (skillnaden mellan maximinivån och den sagda lagerhållningsnivån) inte är en multipel av den definierade multipelkvantiteten, använder Planeringsoptimering det första möjliga värdet som, tillsammans med förutsagd behållningsnivå, kommer att vara under maximinivån. Om summan är mindre än miniminivån använder Planeringsoptimering det första värdet som, tillsammans med förväntad behållning, ligger över maximinivån.

Följande delgrupper innehåller några exempel som visar hur multipeln av orderkvantiteten för en produkt påverkar resultatet av *Min./Max.* lagerpåfyllnadsmetod.

### <a name="example-1"></a>Exempel 1

En produkt har följande konfiguration:

- **Disponeringskod:** *Min./Max.*
- **Minimum:** *15*
- **Maximum:** *22*
- **Flera:** *0*

Det finns 10 stycken i lagerbehållning och det finns ingen annan efterfrågan eller leverans.

När huvudplaneringen körs skapas en planerad order på 12 enheter för att fylla på lagret till maximikvantiteten.

### <a name="example-2"></a>Exempel 2

En produkt har följande konfiguration:

- **Disponeringskod:** *Min./Max.*
- **Minimum:** *15*
- **Maximum:** *22*
- **Flera:** *5*

Det finns 10 stycken i lagerbehållning och det finns ingen annan efterfrågan eller leverans.

När huvudplaneringen körs skapas en planerad order på tio enheter (eftersom 15 påfyllnadsdelar plus 10 lagerdelar överskrider maximikvantiteten).

### <a name="example-3"></a>Exempel 3

En produkt har följande konfiguration:

- **Disponeringskod:** *Min./Max.*
- **Minimum:** *21*
- **Maximum:** *24*
- **Flera:** *5*

Det finns 10 stycken i lagerbehållning och det finns ingen annan efterfrågan eller leverans.

När huvudplaneringen körs skapas en planerad order på tio enheter (eftersom 10 påfyllnadsdelar plus 15 lagerdelar är mindre än minimikvantiteten).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
