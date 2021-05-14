---
title: Viktfälten på beläggningsrader matchar inte viktfälten i beläggningen
description: Viktfälten på beläggningsrader matchar inte viktfälten i beläggningen
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSShipmentDetails_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 639b82a9d46b74f179d6904d2c3b8e7dfb813b58
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924361"
---
# <a name="the-weight-fields-on-load-lines-dont-match-the-weight-fields-on-the-load"></a>Viktfälten på beläggningsrader matchar inte viktfälten i beläggningen

Felkoder: WHSLoadWeightOnLinesDoNotMatchLoadWarning

## <a name="symptoms"></a>Symtom

Systemet visar följande felmeddelande:

> Viktfälten på beläggningsrader matchar inte viktfälten i beläggningen %1. Kör överensstämmelsekontrollen för lagerställets belastningsvikt om du vill räkna om viktfälten.

## <a name="cause"></a>Orsak

Fälten **Nettovikt** och **Tara-vikt** ställs in på *0* (noll) på beläggningsraden. Viktfälten ställs dock inte in på *0* för produktens viktmått. När viktfält inte ställs in på beläggningsraden kan eventuella korrigeringar av kvantiteten på beläggningsraden leda till fel viktberäkning av beläggningen. Det här problemet kan inträffa om vikterna på produkten har ändrats sedan beläggningsraden skapades.

## <a name="resolution"></a>Upplösning

När en beläggningsrad skapas anges som standard viktfälten från produkten på den. Om vikten är noll kan du beräkna om den med hjälp av funktionen för *överensstämmelsekontroll av lagerställets belastningsvikt*.

1. Gå till **Systemadministration \> Periodiska uppgifter \> Databas \> Överensstämmelsekontroll**.
1. I dialogrutan **Överensstämmelsekontroll** anger du fältet **Modul** som *Lagerhantering*.
1. Ange fältet **Kontroll/åtgärd** som *Korrigera fel*.
1. I listan väljer du kryssrutan för **Överensstämmelse för lagerställets belastningsvikt** och ser till att endast raden för denna kryssruta är markerad.
1. Högst upp i kryssrutelistan väljer du ellipsknappen (**...**) och väljer sedan **Dialog** i menyn.
1. I dialogrutan **Överensstämmelsekontroll av överensstämmelse för lagerställes belastningsvikt** anger du följande fält i syfte att ange de kriterier som överensstämmelsekontrollen ska köras för:

    - **Beläggnings-ID:** Ange ett beläggnings-ID. Låt detta fält vara tomt om du vill kontrollera alla inläsnings-ID:er.
    - **Artikelnummer:** Ange ett artikelnummer. Låt detta fält vara tomt om du vill kontrollera alla artiklar.
    - **Räkna alltid om vikt på beläggningar:** Ange detta alternativ som *Ja*.
    - **Tillåt överskrivning av vikt på beläggningsrader:** Ange det här alternativet som *Ja*.

1. Välj **OK** om du vill stänga dialogrutan **Överensstämmelsekontrollen för lagerställets belastningsvikt**.
1. Välj ellipsknappen och sedan **Kör** i menyn.

Vikten räknas om baserat på de kriterier som du har angett. Markera länken **Meddelandeinformation** om du vill visa resultatet av överensstämmelsekontrollen.
