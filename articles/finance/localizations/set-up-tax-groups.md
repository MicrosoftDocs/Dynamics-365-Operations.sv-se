---
title: Ställa in momsgrupper
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
ms.openlocfilehash: 89c5670ee7e78f2dc51f128c3ae8d284bb6b925b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862911"
---
# <a name="set-up-tax-groups"></a>Ställa in momsgrupper

[!include [banner](../includes/banner.md)]

Den här artikeln förklarar hur du ställer in momsgrupper i tjänsten momsberäkning. Här förklaras också hur du ställer in matrisen för tillämplighetsregel för momsgrupp och konfigurerar rader i matrisen.

Begreppet momsgrupper i momsberäkningstjänsten liknar begreppet momsgrupper i Microsoft Dynamics 365 Finance. De är grupper av skattekoder. Tjänsten Skatteberäkning använder skärningspunkten mellan en skattegrupp och en artikelskattegrupp för att fastställa momskoderna.

Momsgrupperna i momsberäkningstjänsten skiljer sig dock från momsgrupperna i Ekonomi eftersom det inte finns några ytterligare parametrar, till exempel **Använd moms** och **Undantagen moms**. I stället är dessa parametrar tillgängliga på skattekodsnivå.

> [!IMPORTANT]
> Inställningen av momsgrupper i momsberäkningstjänsten är juridisk person – oberoende. Du kan bara slutföra den här installationen i RCS (Regulatory Configuration Service) en gång. När du aktiverar tjänsten Momsberäkning i Finance synkroniseras momsgrupper automatiskt för den valda juridiska personen.

## <a name="set-up-a-tax-group"></a>Ställ in en momsgrupp

Följ dessa steg för att skapa en momsgrupp.

1. Logga in på [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).
2. Gå till **Arbetsytor** \> **Globaliseringsfunktioner** \> **Momsberäkning**.
3. Markera den funktion och version som du vill konfigurera och välj **Redigera**.
4. På fliken **Allmänt** välj **Konfigurationsversion**.
5. På fliken **Momsgrupp** väljer du **Hantera kolumn**. Om du ställer in en momsgrupp för första gången ställs fälten i dialogrutan **Hantera kolumn** in automatiskt.
6. Expandera noden **Rader** i listan till vänster och markera kryssrutan för **Momsgrupp**.

    ![Momsgrupp som valts under Radnod i dialogrutan Hantera kolumner.](media/select-tax-group.png)

7. Välj högerpilen för att lägga till **Momsgrupp** till listan **Valda kolumner** till höger.

    ![Momsgrupp som läggs till i listan Markerade kolumner.](media/add-tax-group.png)

8. Välj **OK**.

## <a name="configure-a-tax-group"></a>Konfigurera en momsgrupp

När du har ställt in en momsgrupp skapas matrisen för tillämplighetsregel för momsgrupp. Du kan lägga till rader i matrisen om du vill konfigurera momsgruppen.

1. På fliken **Momsgrupp** väljer du **Lägg till**.
2. Ange namn på momsgruppen i fältet **Momsgrupp**.

    > [!IMPORTANT]
    > Vi rekommenderar att du begränsar namnet på momsgruppen till 10 tecken. Det här namnet synkroniseras med Finance, som har en gräns på 10 tecken för namnen på momsgrupper.

3. Markera kryssrutan för varje momskod som du vill inkludera i momsgruppen i fältet **Momskoder**. Du kan ta med flera momskoder i en momsgrupp.

    ![Flera momskoder som valts i fältet Momskoder.](media/multiple-tax-codes-selection.png)

4. Upprepa steg 1 till och med 3 om du vill lägga till fler momsgrupper.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
