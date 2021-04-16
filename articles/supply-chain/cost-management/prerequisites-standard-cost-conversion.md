---
title: Förutsättningar för en standardkostnadskonvertering
description: I det här avsnittet beskrivs hur du utför uppgifter, innan du kör en standardkostnadskonvertering.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: 50891
ms.assetid: 73af66cf-c924-45be-837a-a648dbd05a31
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b78cfb2c6f0462a86cf3785038c5fe4e5d63b9cf
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809696"
---
# <a name="prerequisites-for-a-standard-cost-conversion"></a>Förutsättningar för en standardkostnadskonvertering

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du utför uppgifter, innan du kör en standardkostnadskonvertering. 

Gör på följande sätt innan du kör en standardkostnadkonvertering:

1.  Definiera en **Lagermodellgrupp** för standardkostnader. Använd sidan Artikelmodellgrupp för att skapa en artikelmodellgrupp som använder lagermodell med standardkostnad. När du ställer in en standardkostnadskonvertering kan du tilldela den här artikelmodellgruppen för de artiklar som konverteras.
2.  Tilldela en **kostnadsgrupp** till varje artikel.
    -   Den kostnadsgrupp som tilldelas en inköpt artikel, kan fungera som grund för tilldelning av redovisningskonton som hör till standardkostnader. Detta kan omfatta att tilldela redovisningskonton för inköpsprisavvikelser. I en tillverkningsmiljö ger kostnadsgruppen som tilldelas en inköpt komponent också underlaget för kostnadssegmenteringen i de beräknade kostnaderna för en tillverkad artikel.
    -   Den kostnadsgrupp som tilldelas för en tillverkad artikel kan fungera som grund för tilldelning av redovisningskonton som är relaterade till standardkostnader, t.ex. för att tilldela redovisningskonton för produktionsavvikelser.

3.  Tilldela en **standardorderkvantitet** för en tillverkad artikel när den har konstanta kostnader. Standardorderkvantiteten för en tillverkad artikel fungerar som en redovisningspartistorlek för amortering eller allokering, konstantkostnader. Dessa kan inkludera inställningstider i flödesoperationer eller en konstant komponentkvantitet i en strukturlista (BOM).
4.  Tilldela **redovisningskonton** som är relaterade till standardkostnader, särskilt omvärderingsavvikelsen. Använd sidan **Bokföring**(**Lagerhantering** &gt; **Inställning**) för att tilldela redovisningskonton som är relaterade till standardkostnader. För en process för standardkostnadskonvertering måste du (som ett minimikrav) tilldela kontot för omvärderingsavvikelsen för alla artiklar och alla kostnadsgrupper. Använd sidan **Kontoplan** för att definiera de redovisningskonton som kommer att behövas för standardkostnader. Använd sidan **Transaktionskombinationer** om vill du göra det möjligt att använda kostnadsrelationer (för tabeller, grupper och alla) innan du definierar artikelbokföringsregler.
5.  Definiera de lagerparametrar som hör till standardkostnader. Använd fliken **Nummerserier** på sidan **Parametrar för hantering av lager och lagerstyrning** för att tilldela en nummerserie för omvärderingsverifikationer. En omvärderingsverifikation skapas när standardkostnadskonverteringen skapar en förändring av lagervärdet för en artikel. Använd sidan **Parametrar för hantering av lager och lagerstyrning** för att definiera parametrar för kostnadskontroll (på fliken **Lagerredovisning**) för att definiera två parametrar som hör till standardkostnader.
    -   Använd fältet **Kostnadsuppdelning** för att välja Ingen eller Delredovisning. Valet av Delredovisning benämns som en aktiv kostnadsuppdelning. En aktiv kostnadsuppdelning har stor betydelse när du beräknar, behåller och visar kostnadsgruppssegmentering över en produktstruktur i flera nivåer för standardkostnadsartiklar. När den kostnadskalkylerade uppdelningen är aktiv, kan du rapportera och analysera följande på en enda nivå, flera nivåer eller i totalformat:
        1.  Lager
        2.  Produkter i arbete (PIA)
        3.  Kostnader för sålda varor (KSV) per kostnadsgrupp

        En aktiv kostnadsuppdelning innebär också att en aktivering av en tillverkad artikels kostnad leder till att kostnadsgruppssegmenteringen lagras inom artikelns kostnadspost. Om du inte anger ett värde i fältet **Kostnadsuppdelning** innebär det att kostnadsgruppssegmenteringen inte underhålls för standardkostnadsartiklar. En tillverkad artikels standardkostnad beräknas och underhålls därför som ett enskilt belopp utan kostnadsgruppssegmentering, och kostnadsbidragen från tillverkade komponenter aggregeras till ett enda belopp.
    -   Använd fältet **Avvikelser från standard** om du vill välja summerad eller per kostnadsgrupp. Valet av per den kostnadskalkylerade gruppen låter dig identifiera inköpsprisavvikelser och produktionsavvikelser per den kostnadskalkylerade gruppen. Detta låter dig även identifiera fyra typer av produktionsavvikelser (partistorlek, kvantitet, pris och ersättning). Om du väljer summerad kan du inte identifiera avvikelser per kostnadsgrupp, och du kan inte identifiera de fyra typerna av produktionsavvikelse. Du kan bara visa en summerad produktionsavvikelse. Principen om avvikelse från standarden fungerar oberoende av kostnadsuppdelningsprincipen. Det innebär att du kan välja en kostnadsuppdelningsprincip som är ingen, och välja avvikelser per kostnadsgrupp, så att produktionsavvikelser per kostnadsgrupp ändå kan fångas in.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]