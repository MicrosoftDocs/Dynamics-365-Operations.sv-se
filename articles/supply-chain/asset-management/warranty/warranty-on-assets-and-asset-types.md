---
title: Garanti på tillgångar och tillgångstyper
description: Det här avsnittet förklarar hur du ställer in garantier på tillgångar och tillgångstyper i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 78ac93b1e681fca7d7eefd921f282a8496aa9d0a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5245333"
---
# <a name="warranties-on-assets-and-asset-types"></a>Garanti på tillgångar och tillgångstyper

[!include [banner](../../includes/banner.md)]

 


Det här avsnittet förklarar hur du ställer in garantier på tillgångar och tillgångstyper i Tillgångshantering.

## <a name="set-up-a-warranty-on-an-asset-type"></a>Ställa in garanti på en tillgångstyp

1. Välj **tillgångshantering** \> **inställningar** \> **tillgångstyper** \> **tillgångstyper**.
2. I det vänstra fönstret väljer du den tillgångstyp att koppla ett leverantörsgarantiavtal till och väljer sedan **Standardtyp för tillgång**.
3. Välj avtalet på snabbfliken **Allmänt**, i fältet **Leverantörsgaranti**.

## <a name="set-up-a-warranty-on-an-asset"></a>Ställa in garanti på en tillgång

1. Välj **Tillgångshantering** \> **Allmänt** \> **Tillgångar** \> **Alla tillgångar**
2. Välj tillgången och välj **Redigera.**
3. På snabbfliken **Leverantör** i avsnittet **Leverantörsgaranti** väljer du garantiavtalet i fältet **Garanti**.
4. Välj start- och slutdatum i fälten **Garantistart** och **Garantislut**.

    > [!IMPORTANT]
    > Om ett datum har valts i fältet **Garantistart** på en arbetsorder, blir garantin giltigt för arbetsordern på det datumet. När du skapar en arbetsorder anges fältet **Garantistart** automatiskt till skapandedatumet. Du kan dock ändra datumet så att det motsvarar t.ex. startdatum för ett garantiavtal.
    >
    > ![Sidan Arbetsorder](media/02-warranty.png)

> [!NOTE]
> När du skapar en arbetsorder för en tillgång som täcks av en leverantörsgaranti, och arbetsordern har ett förväntat startdatum under garantiperioden, får du ett meddelande om garantiavtalet. Du kan sedan avbryta arbets ordern efter behov.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]