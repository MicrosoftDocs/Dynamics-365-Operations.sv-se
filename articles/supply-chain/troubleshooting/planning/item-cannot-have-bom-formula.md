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
ms.openlocfilehash: 1e946adc3a04db60bf15ac7bb44163085e1c19802872964877d3929b1f79bf7d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730116"
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
