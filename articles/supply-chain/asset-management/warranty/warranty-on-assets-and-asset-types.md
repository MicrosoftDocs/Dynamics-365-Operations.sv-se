---
title: Garanti på tillgångar och tillgångstyper
description: Denna artikel förklarar hur du konfigurerar garantier för tillgångar och tillgångstyper i Tillgångshantering.
author: johanhoffmann
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fa4fe7af46996e8de76ea61d5395327e7617e736
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906136"
---
# <a name="warranties-on-assets-and-asset-types"></a>Garanti på tillgångar och tillgångstyper

[!include [banner](../../includes/banner.md)]

 


Denna artikel förklarar hur du konfigurerar garantier för tillgångar och tillgångstyper i Tillgångshantering.

## <a name="set-up-a-warranty-on-an-asset-type"></a>Ställa in garanti på en tillgångstyp

1. Välj **Tillgångshantering** \> **inställningar** \> **tillgångstyper** \> **tillgångstyper**.
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
    > ![Sidan Arbetsorder.](media/02-warranty.png)

> [!NOTE]
> När du skapar en arbetsorder för en tillgång som täcks av en leverantörsgaranti, och arbetsordern har ett förväntat startdatum under garantiperioden, får du ett meddelande om garantiavtalet. Du kan sedan avbryta arbets ordern efter behov.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]