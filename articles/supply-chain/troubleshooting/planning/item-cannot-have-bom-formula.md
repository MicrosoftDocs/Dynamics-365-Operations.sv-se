---
title: En artikel kan inte ha en strukturlista eller en formel
description: När du försöker bekräfta en order visas ett felmeddelande under artikelvalidering. Den visar att artikeln inte kan ha någon strukturlista eller en formel.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6739b8b1e4d080055a2a0501427eac1c2e8a96c5
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294182"
---
# <a name="item-cant-have-a-bom-or-formula"></a>En artikel kan inte ha en strukturlista eller en formel

Felkod: PRO2614

## <a name="symptoms"></a>Symtom

När du försöker bekräfta en order visas ett felmeddelande under artikelvalidering:

> Ingen strukturlista eller formel kan användas för artikeln

## <a name="resolution"></a>Lösning

Artiklar som har en strukturlista eller en formel måste vara av typen *Planeringsartikel*, *Strukturlista* eller *Formel*. Följ dessa steg för att ändra typen av ett objekt.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Öppna relevanta produkt.
1. På snabbfliken **Konstruera** ange fältet **Produktionstyp** till *Planera artikel*, *strukturlista* eller *formel*.
