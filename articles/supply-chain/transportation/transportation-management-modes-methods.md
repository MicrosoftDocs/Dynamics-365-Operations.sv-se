---
title: Transportföretagslägen och metoder
description: I denna artikel beskrivs hur du konfigurerar lägen och metoder för transporthantering.
author: Weijiesa
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1daed8940e41af0163b90195eed64464c2dcac0b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900750"
---
# <a name="transportation-management-modes-and-methods"></a>Transportföretagslägen och metoder

[!include [banner](../includes/banner.md)]

Transporthanteringsläget representerar typen av transport som transportföretaget använder för fraktleveranser, till exempel hel lastbilslast, mindre än en lastbilslast eller paket. Transportmetoden representerar det transportsätt som transportföretaget använder för fraktleveranser, till exempel luft, land, hav eller järnväg.

Lägen och transportmetoder används i flera sammanhang. Endast lägen används i flödesplaner, medan både lägen och transportmetoder används när transportföretag och transportföretagstjänster ställs in. Det finns ingen explicit relation eller hierarki mellan lägen och transportmetoder.

## <a name="create-a-mode"></a>Skapa ett läge

Gör så här om du vill skapa ett läge:

1. Gå till **Transporthantering \> Inställningar \> Leverantörer \> Läge**.
1. Välj **Nytt** för att skapa ett nytt läge.
1. Ange ett unikt ID och ett beskrivande namn på läget.
1. Stäng sidan.

## <a name="create-a-transportation-method"></a>Skapa en transportmetod

Följ dessa steg för att skapa en transportmetod:

1. Gå till **Transporthantering \> Inställningar \> Transportföretag \> Transportmetoder**.
1. Klicka på **Ny** om du vill skapa en ny tranportmetod.
1. Ange ett unikt ID och ett beskrivande namn på transportmetoden.
1. Stäng sidan.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]