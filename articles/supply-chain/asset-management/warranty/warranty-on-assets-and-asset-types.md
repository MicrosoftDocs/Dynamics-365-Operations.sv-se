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
ms.openlocfilehash: 2e63161aa32ecbc99baace9bb0cc649aedc600ed
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016004"
---
# <a name="warranties-on-assets-and-asset-types"></a>Garanti på tillgångar och tillgångstyper

[!include [banner](../../includes/banner.md)]

 


Denna artikel förklarar hur du konfigurerar garantier för tillgångar och tillgångstyper i Tillgångshantering.

## <a name="set-up-a-warranty-on-an-asset-type"></a>Ställa in garanti på en tillgångstyp

1. Välj **Tillgångshantering** \> **inställningar** \> **tillgångstyper** \> **tillgångstyper**.
2. I det vänstra fönstret väljer du den tillgångstyp att koppla ett leverantörsgarantiavtal till och väljer sedan **Standardtyp för tillgång**.
3. Välj avtalet på snabbfliken **Allmänt**, i fältet **Leverantörsgaranti**.

## <a name="set-up-a-warranty-on-an-asset"></a>Ställa in garanti på en tillgång

1. Välj **Tillgångshantering** \> **Tillgångar** \> **Alla tillgångar**.
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