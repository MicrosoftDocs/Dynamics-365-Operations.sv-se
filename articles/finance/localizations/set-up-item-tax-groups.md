---
title: Ställ in artikelmomsgrupper
description: Den här artikeln förklarar hur du ställer in momsgrupper i tjänsten momsberäkning.
author: wangchen
ms.date: 11/30/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 3bc705bc8173ad2bc8ef883e6dc80b0a187314ad
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846475"
---
# <a name="set-up-item-tax-groups"></a>Ställ in artikelmomsgrupper

[!include [banner](../includes/banner.md)]

Den här artikeln förklarar hur du ställer in momsgrupper i tjänsten momsberäkning. Här förklaras också hur du ställer in matrisen för tillämplighetsregel för artikelmomsgrupp och konfigurerar rader i matrisen.

Begreppet artikelmomsgrupper i momsberäkningstjänsten liknar begreppet artikelmomsgrupper i Microsoft Dynamics 365 Finance. De är grupper av skattekoder. Tjänsten Skatteberäkning använder skärningspunkten mellan en skattegrupp och en artikelskattegrupp för att fastställa momskoderna.

> [!IMPORTANT]
> Inställningen av artikelmomsgrupper i momsberäkningstjänsten är juridisk person – oberoende. Du kan bara slutföra den här installationen i RCS (Regulatory Configuration Service) en gång. När du aktiverar tjänsten Momsberäkning i Finance synkroniseras artikelmomsgrupper automatiskt för den valda juridiska personen.

## <a name="set-up-an-item-tax-group"></a>Ställ in artikelmomsgrupp 

Följ stegen för att ställa in en artikelmomsgrupp:

1. Logga in på [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).
2. Gå till **Arbetsytor** \> **Globaliseringsfunktioner** \> **Momsberäkning**.
3. Markera den funktion och version som du vill konfigurera och välj **Redigera**.
4. På fliken **Allmänt** välj **Konfigurationsversion**.
5. På fliken **Artikelmomsgrupp** väljer du **Hantera kolumn**. Om du ställer in en artikelmomsgrupp för första gången ställs fälten i dialogrutan **Hantera kolumn** in automatiskt.
6. Expandera noden **Rader** i listan till vänster och markera kryssrutan för **Artikelmomsgrupp**.

    ![Artikelmomsgrupp som valts under Radnod i dialogrutan Hantera kolumner.](media/select-item-tax-group.png)

7. Välj högerpilen för att lägga till **Artikelmomsgrupp** till listan **Valda kolumner** till höger.

    ![Artikelmomsgrupp som läggs till i listan Markerade kolumner.](media/add-item-tax-group.png)

8. Välj **OK**.

## <a name="configure-an-item-tax-group"></a>Ställ in artikelmomsgrupp

När du har ställt in en artikelmomsgrupp skapas matrisen för tillämplighetsregel för momsgrupp. Du kan lägga till rader i matrisen om du vill konfigurera artikelmomsgruppen.

1. På fliken **Artikelmomsgrupp** väljer du **Lägg till**.
2. Ange namn på artikelmomsgruppen i fältet **Artikelmomsgrupp**.

    > [!IMPORTANT]
    > Vi rekommenderar att du begränsar namnet på artikelmomsgruppen till 10 tecken. Det här namnet synkroniseras med Finance, som har en gräns på 10 tecken för namnen på artikelmomsgrupper.

3. Markera kryssrutan för varje momskod som du vill inkludera i artikelmomsgruppen i fältet **Momskoder**. Du kan ta med flera momskoder i en artikelmomsgrupp.

    ![Flera momskoder som valts i fältet Momskoder.](media/multiple-tax-codes-selection.png)

4. Upprepa steg 1 till och med 3 om du vill lägga till fler artikelmomsgrupper.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
