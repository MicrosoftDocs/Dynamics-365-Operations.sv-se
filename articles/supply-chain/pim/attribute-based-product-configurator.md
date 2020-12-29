---
title: Attributbaserade försäljningspriser för begränsningsbaserad produktkonfiguration
description: I det här avsnittet beskrivs hur du skapar försäljningsprismodeller med försäljningspriser baserade på komponenter och attribut i stället för på den fysiska strukturlistan och flödet.
author: sorenva
manager: tfehr
ms.date: 10/2/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2020-08-17
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: c0f9c1bb94b4dcc3c3c1e7656868ef6e6bd903db
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437333"
---
# <a name="attribute-based-sales-prices-for-constraint-based-product-configuration"></a>Attributbaserade försäljningspriser för begränsningsbaserad produktkonfiguration

I det här avsnittet beskrivs hur du skapar försäljningsprismodeller med försäljningspriser baserade på komponenter och attribut i stället för på den fysiska strukturlistan och flödet. Du kan skapa flera försäljningsprismodeller för varje produktkonfigurationsmodell.

## <a name="set-relevant-product-information-management-parameters"></a>Ange relevanta parametrar för produktinformationshantering

Innan du börjar bygga dina prismodeller måste du definiera en standardvaluta som används när du bygger dina försäljningsprismodeller. Du kan också välja om du vill bifoga en Microsoft Excel-fil med en prisuppdelning för alla order- eller offertrader. Med prisuppdelningen låter dig dela information med kunder om hur du har kommit till ett visst försäljningspris för en konfigurerad produkt.

Så här anger du standardvalutan:

1. Gå till **Produktinformationshantering \> Konfigurera \> Parametrar för produktinformationshantering**.
1. Öppna fliken **begränsningsbaserade produktkonfigurationsmodeller**.
1. Öppna listrutan **standardvaluta** och välj din valuta.

    ![Ange standardvaluta för begränsningsbaserad produktkonfiguration](media/prod-config-currency.png "Ange standardvaluta för begränsningsbaserad produktkonfiguration")

1. Om du vill bifoga en Excel-fil med en prisuppdelning för alla order- eller offertrader anger du **Prismodell**, **Koppla** till *Ja*.

## <a name="build-your-sales-price-models"></a><a name="build-price-model"></a>Bygga dina försäljningsprismodeller

Bygga en försäljningsprismodell:

1. Gå till **Produktinformationshantering \> Produkter \> Produktkonfigurationsmodeller**.
1. Välj målmodellen för produktkonfiguration.
1. I åtgärdsfönstret, öppna fliken **Modell** och från gruppen **Konfigurera** välj **Prismodeller**.
1. Sidan **prismodell** öppnas.
1. Välj en prismodell eller lägg till en ny i rutnätet.
1. Välj **Redigera** om du vill öppna sidan redigera för den valda modellen, som innehåller följande funktioner:
    - I sidhuvudet i formuläret visas standardvalutan och du kan lägga till nya valutor för prisinställningen.
    - I det vänstra fönstret visas alla komponenter och användarkrav för produktmodellen. Varje nod i produktmodellträdet kan ha ett basprisuttryck och ett valfritt antal uttrycksregler. En uttrycksregel består av ett villkor och ett uttryck och varje uttrycksregel omfattar ett produktalternativ som hjälper till att kontrollera produktens pris.
    - När du bygger dina villkor och uttryck har du samma operatorer tillgängliga som för beräkningar i en produktmodell. Uttrycksredigeraren stöder också både villkor och uttryck.
1. Välj en nod i den vänstra kolumnen och använd sedan de funktioner som beskrivs i föregående steg för att fastställa prisregler för den (se även exemplet som medföljer efter den här proceduren). Upprepa det här steget för varje nod om det behövs.

Följande exempel visar ett baspris med ett statiskt antal 899,95 EUR, som kan ändras av en eller flera av följande fem uttrycksregler, beroende på konfigurationen som valts av kunden:

- För skåp med vit yta subtraherar du 59,95 EUR.
- För hörnskydd lägger du till 35,95 EUR.
- För ett metallgaller lägger du till 89,95 EUR.
- För skåp i rosenträ lägger du till 119,95 EUR.
- Lägg till 12,95 EUR för varje enhet av högtalarhöjd.

![Exempel på prismodell](media/prod-config-rules-example.png "Exempel på prismodell")

## <a name="add-support-for-multiple-currencies"></a>Lägg till stöd för flera valutor

När en konfigurerbar produkt säljs, kontrollerar systemet om priserna har ställts in uttryckligen i kundvalutan. I så fall används explicita värden. Annars använder systemet de valutakurser som har fastställts för försäljningsföretaget för att konvertera standardvalutavärdet till kundens valuta.

Så här lägger du till uttryckliga priser i en alternativ valuta:

1. Öppna sidan redigera för prismodellen enligt beskrivningen i [skapa försäljningsprismodeller](#build-price-model).
1. Välj knappen **Lägg till** i prismodellens rubrik för att öppna listrutan **valutor** som innehåller de tillgängliga valutorna.
1. Välj den valuta du vill lägga till i listrutan **Valutor** och välj sedan **OK**.
1. Listrutan **aktuell valuta** innehåller nu den valuta som du just har lagt till, plus eventuella andra valutor som tidigare har lagts till. Markera din nya valuta och lägg märke till att rutnätet i avsnittet **uttrycksregler** innehåller nu två uttrycksfält:
    - **Uttryck** - visar det uttryck (eller konstant värde) som används för att söka efter priset med den valda valutan för den **aktuella valutan**.
    - **Standarduttryck** - visar det uttryck (eller konstant värde) som används för att söka efter priset med standardvalutan (visas i fältet **standardvaluta**).

    > [!NOTE]
    > Fältet **Villkor** för uttrycksreglerna "ägs" av standardvalutan, vilket innebär att du inte kan ändra villkoret för andra valutor. Du kan inte heller lägga till nya uttrycksregler när en annan valuta än standardvalutan har valts som den **aktuella valutan**.
1. Redigera värden i kolumnen **uttryck** efter behov för den aktuella valutan.

I exemplet nedan _EUR_ är standardvalutan och _USD_ har lagts till som en extra valuta.

![Exempel på en modell med flera valutor](media/prod-config-rules-currency-example.png "Exempel på en modell med flera valutor")

> [!NOTE]
> Du kan inte lägga till uttrycksregler som är unika för en valuta som inte är standard. Om du vill skapa uttrycksregler som bara är relevanta för en annan valuta än standardvalutan ställer du in prisuttrycket för standardvalutan till noll. Ställ sedan in lämpligt uttryck för valutan som inte är standard.

## <a name="test-your-price-model"></a>Testa prismodellen

Om du vill testa hur försäljningspriserna fungerar i en konfiguration öppnar du din prismodells redigeringssida, enligt beskrivningen i [skapa försäljningsprismodeller](#build-price-model) och väljer sedan **test** i åtgärdsfönstret. Dialogrutan **Testa produktmodellen** öppnas där du kan göra följande:

- Använd de konfigurationsinställningar som erbjuds här för att välja produktalternativ och se hur de påverkar det värde som visas för **pris och leveransdatum**.
- Välj **Visa prisuppdelning** du vill hämta ett Excel-dokument som visar fullständiga detaljer om hur priset beräknades.

![Testa din produktmodellen](media/prod-config-test.png "Testa din produktmodellen")

Det hämtade kalkylbladet visar både det absoluta värdet och bidraget som en procentsats för varje aktivt priselement. Om du har ställt in alternativet **Koppla** prismodell på sidan **Parametrar för produktinformationshantering** kopplas det här Excel-bladet till order- eller offertraden.

![Excel-kalkylblad som visar prisuppdelning](media/prod-config-excel-example.png "Excel-kalkylblad som visar prisuppdelning")

## <a name="set-up-selection-criteria-for-price-models"></a>Ställ in urvalskriterier för prismodeller

När prismodellerna är på plats måste du fastställa minst ett urvalskriterium för att kunna plocka upp prismodellen när du konfigurerar till offert eller order. Du ska göra detta genom att ställa in en eller flera frågor. I en kombination med matchande försäljningsprismodeller ger frågorna stor flexibilitet vid mål för försäljningspriser för vissa kunder, regioner, perioder och andra kriterier.

Ställ in urvalskriterier för prismodeller:

1. Gå till **Produktinformationshantering \> Produkter \> Produktkonfigurationsmodeller**.
1. Välj målmodellen för produktkonfiguration.
1. I åtgärdsfönstret, öppna fliken **Modell** och från gruppen **Konfigurera** välj **Prismodellkriterier**. Sidan **prismodellkriterier** öppnas.
1. Om raden som du behöver inte finns ännu, väljer du **Ny** i åtgärdsfönstret för att lägga till en ny rad i rutnätet och gör följande inställningar:
    - **Namn** - Ange ett namn för denna rad.
    - **Beskrivning** - beskriver kort frågan och vad den gäller.
    - **Prismodell** - Välj en [prismodell](#build-price-model) (från den aktuella konfigurationsmodellen) som frågan gäller när den utlöses.
    - **Order typ** - Välj den typ av order där frågan ska gälla.
    - **Giltigt från** - Ange första dagen då frågan ska gälla.
    - **Förfaller den** - Ange det sista datum då frågan ska gälla.

    ![Prismodellvillkor](media/prod-config-price-model-criteria.png "Prismodellvillkor")

1. Markera raden för den fråga som du vill definiera och välj sedan **Redigera** i **Åtgärdsfönstret**. Dialogrutan frågedesigner öppnas. Den fungerar på samma sätt som de flesta frågedesigners i Supply Chain Management. Använd det för att definiera de villkor under vilka prismodellen för den valda raden ska användas.

1. Upprepa steg 4-5 för varje fråga som du behöver.
    > [!TIP]
    > Du kan spara tid genom att kopiera en befintlig rad som redan liknar den nya som du vill lägga till. Det gör du genom att markera en målsida och sedan välja **duplicera** i åtgärdsfönstret.

1. När du har ställt in dina kriterier ordnar du dem i rätt ordning i listan **prismodellkriterier**. Om du vill flytta en rad markerar du raden och väljer **upp** eller **ned** i åtgärdsfönstret.

    > [!IMPORTANT]
    > Vid konfigurationstillfället startar systemet sökningen från överst i listan och använder den första frågan som matchar data på offert- eller orderraden. Därför måste du placera dina mest specifika frågor överst. Om du lägger till en allmän fråga överst i listan, är det här den som används även om en fråga kan finnas längre ned i listan som är mål för den exakta kunden eller den potentiella kunden för konfigurationen.

## <a name="set-attribute-based-sales-prices-for-the-product-model-version"></a>Se attributbaserade försäljningspriser för produktmodellversionen

Det sista steget är att ange de attributbaserade försäljningspriserna för produktmodellversionen. Om du vill göra det här:

1. Gå till **Produktinformationshantering \> Produkter \> Produktkonfigurationsmodeller**.
1. Välj målmodellen för produktkonfiguration.
1. I åtgärdsfönstret, öppna fliken **Modell** och från gruppen **Produktmodellinformation** välj **Versioner**.
1. Sidan **versioner** öppnas. Kontrollera att **prissättningsmetoden** är inställd på **attributbaserat**.
    ![Ställ in prissättningsmetoden för attributbaserad](media/prod-config-versions.png "Ställ in prissättningsmetoden för attributbaserad")
