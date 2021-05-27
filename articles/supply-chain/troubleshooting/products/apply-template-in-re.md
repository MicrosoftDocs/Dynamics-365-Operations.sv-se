---
title: Du kan inte använda en mall på en frisläppt produkt
description: Du kan inte använda en mall på en frisläppt produkt.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ad6efdced9bce924fbf5bc207c92fa2c3a6c79d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026908"
---
# <a name="you-cant-apply-a-template-to-create-a-released-product"></a>Du kan inte använda en mall för att skapa en frisläppt produkt

KB-nummer: 4612097

## <a name="symptoms"></a>Symtom

När du skapar en ny frisläppt produkt med hjälp av dialogrutan **Ny frisläppt produkt** kan du välja en mall. Mallen bör innehålla standardinställningar för många fält i den nya frisläppta produkten. Vissa eller alla fält anges dock inte när du har valt mallen.

## <a name="cause"></a>Orsak

På många sidor i Microsoft Dynamics 365 Supply Chain Management kan du skapa en mall som fastställer de första inställningarna för de poster som visas på dessa sidor. Du kan skapa en av dessa mallar genom att välja **Postinfo** under fliken **Alternativ** i åtgärdsfönstret. Frisläppta produkter är dock mycket mer komplexa än de flesta andra typer av poster. Även om du kan välja **Postinfo** på sidan **Frisläppta produkter** för att skapa en mall, och även om du kan välja mallen när du skapar en frisläppt produkt, innehåller inte mallen de förväntade fältvärdena för den nya frisläppta produkten. Därför kan du inte använda "postinformation"-mallar för frisläppta produkter. I stället måste du skapa dedikerade produktmallar.

## <a name="resolution"></a>Upplösning

För att skap en produktmall använder du menyn **Mall** under fliken **Produkt** i åtgärdsfönstret, inte knappen **Postinfo** under fliken **Alternativ**.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. I åtgärdsfönstret, under fliken **Produkt**, i gruppen **Ny**, väljer du **Mall** och sedan antingen **Skapa personlig mall** eller **Skapa delad mall**, beroende på vad som är lämpligt.
