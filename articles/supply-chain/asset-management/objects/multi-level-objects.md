---
title: Tillgångar på flera nivåer
description: Denna artikel beskriver hur du skapar och tar bort tillgångar på flera nivåer.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b13db8b8b12aaef2e067f9a55eb8754333eb16b
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2022
ms.locfileid: "9017157"
---
# <a name="multi-level-assets"></a>Tillgångar på flera nivåer

[!include [banner](../../includes/banner.md)]

 

Denna artikel beskriver hur du skapar och tar bort tillgångar på flera nivåer. Du kan skapa tillgångar och relaterade undertillgångar i en hierarkisk trädstruktur. På så sätt kan du visa relationer och beroenden mellan tillgångar. Underhållsjobb kan relateras till alla nivåer i trädstrukturen. Statistik kan också skapas för en individuell nivå eller som en summa av alla nivåer av undertillgångar.

På listsidan **Alla tillgångar** (**Tillgångshantering** \> **Tillgångar** \> **Alla tillgångar**), **Tillgångar** tillgångar hierarkisk ordning. Kolumnen **överordnade** visar den relaterade överordnade. Dessutom, om tillgångar och undertillgångar redan har skapats visar avsnittet **Tillgångsträd** i fönstret **Relaterad information** tillgången i trädstrukturen.

Information om hur du skapar en tillgång finns i [Skapa en tillgång](../objects/create-an-object.md). Om du vill skapa en undertillgång väljer du den den överordnade tillgången i fältet **överordnad** på snabbfliken **allmänt**.

## <a name="copy-an-asset-or-asset-structure"></a>Kopiera en tillgång eller tillgångsstruktur

Om ditt företag har flera liknande tillgångsstrukturer, kan du använda funktionen Kopiera i Tillgångshantering för att snabbt skapa dem.

1. Välj **Tillgångshantering** \> **Tillgångar** \> **Alla tillgångar**.
2. På listsidan **Alla tillgångar** väljer du den tillgång som ska kopieras. Om du till exempel vill kopiera hela tillgångsstrukturen, inklusive undertillgångar, väljer du en överordnad tillgång.
3. Välj **Kopiera tillgång**. I avsnittet **Kopiera från** är fältet **Tillgång** inställt på den tillgång som du valde på listsidan.
4. I avsnittet **Kopiera till** i fältet **Tillgång** anger du namnet på den nya tillgången.
5. Om den tillgång som du skapar ska vara en del av en befintlig tillgångsstruktur, i avsnittet **Överordnad tillgång** i fältet **Tillgång** väljer du ett överordnat ID.
6. Välj **OK**. Den nya tillgångsstrukturen visas på listsidan **Alla tillgångar**. Alla tillgångsattribut, underhållsplaner och underhållsomgångar som är relaterade till den tillgång som du kopierade överförs till den nya tillgången eller tillgångsstrukturen.

När du kopierar en tillgångsstruktur har undertillgångarna i den nya strukturen samma namn som undertillgångarna du kopierade. När kopieringen är klar kan du enkelt ändra namn och andra inställningar för en tillgång. Välj tillgången på listsidan **Alla tillgångar** och välj sedan knappen **redigera**.

> [!NOTE]
> När du kopierar en tillgång eller tillgångsstruktur återställs livscykeltillståndet för de nya tillgångarna till det tillstånd som du definierade som det ursprungliga livscykeltillståndet för tillgångarna. Funktionsplatsen återställs till standardfunktionsplatsen.

## <a name="delete-an-asset-or-asset-structure"></a>Ta bort en tillgång eller tillgångsstruktur

Om en tillgång har relaterade undertillgångar kan du endast ta bort den om inga underhållsbegäran, arbetsorderjobb, felregistreringar eller villkorsbedömningar registreras på någon av tillgångarna.

1. På listsidan **Alla tillgångar** väljer du den tillgång som ska tas bort.
2. Välj **Ta bort**.

> [!NOTE]
> Om du inte kan ta bort en tillgång med hjälp av den här proceduren är ett annat sätt att hantera borttagningen att konfigurera ett tillgångs livscykeltillstånd för detta ändamål. Du kan till exempel konfigurera ett **Kasserat** eller **Borttaget** livscykeltillstånd på sidan **Tillgångens livscykeltillstånd**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]