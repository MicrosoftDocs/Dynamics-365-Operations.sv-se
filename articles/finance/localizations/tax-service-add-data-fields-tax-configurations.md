---
title: Lägga till datafält i momskonfigurationer
description: I det här avsnittet beskrivs hur du anpassar momskonfigurationer genom att lägga till datafält.
author: kailiang
ms.date: 03/25/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: b9d9fce81151ad70d57c69e389e238a6f9137d56
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819434"
---
# <a name="add-data-fields-in-tax-configurations"></a>Lägga till datafält i momskonfigurationer

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

I det här avsnittet beskrivs hur du anpassar momskonfigurationer med hjälp av [datafält som läggs till i momsintegreringen](tax-service-add-data-fields-tax-integration-by-extension.md).

## <a name="customize-the-tax-data-model"></a>Anpassa momsdatamodellen

1. I Microsoft Dynamics 365 Finance, gå till **Elektronisk rapportering** \> **Momskonfigurationer**.
2. I konfigurationsträdet väljer du **Momsdatamodell - Europa**. Klicka på **Skapa konfiguration** i åtgärdsfönstret.
3. I listrutan, välj alternativet **Beskattningsbar dokumentmodell härledd från Namn: Momsdatamodell - Europa, Microsoft**, ange ett namn för den nya momsdatamodellen och välj sedan **Skapa konfiguration**.
4. Välj den momsdatamodell som du just skapat och markera sedan **Designer** i åtgärdsfönstret.
5. Expandera datamodellträdet, välj **Rader** och välj sedan **Ny**.
6. Ange ett namn i dialogrutan **Skapa nod**, ange artikeltypen och välj sedan **Lägg till**.
7. Lägg till alla kolumner som behövs.
8. I åtgärdsrutan väljer du **Spara** och välj sedan **Slutför**.
9. Stäng sidan och visa den fullständiga versionen av din momsdatamodell.

## <a name="customize-the-tax-configuration"></a>Anpassa momskonfiguration

1. I Finance , gå till **Elektronisk rapportering** \> **Momskonfigurationer**.
2. I konfigurationsträdet väljer du **Momskonfiguration - Europa**. Klicka på **Skapa konfiguration** i åtgärdsfönstret.
3. I listrutan, välj alternativet **Momstjänstkonfiguration härledd från Namn: Momskonfiguration - Europa, Microsoft** ange ett namn för den nya skattekonfigurationen och välj sedan **Skapa konfiguration**.
4. Välj den momskonfiguration som du just skapat och markera sedan **Designer** i åtgärdsfönstret.
5. I avsnitt **Egenskaper** i fältet **Datamodell** välj den anpassade momsdatamodellen som du skapade tidigare.
6. I fältet **Datamodellversion**,välj den färdiga versionen av momsdatamodellen.
7. Välj **Lägg till** och lägg till de obligatoriska momsmåtten.
8. I åtgärdsrutan väljer du **Spara** och välj sedan **Slutför**.
9. Stäng sidan och visa den fullständiga versionen av din momskonfiguration.

## <a name="implement-tax-features-in-the-customized-tax-configuration"></a>Implementera momsfunktioner i den anpassade momskonfigurationen

1. I Regulatory Configuration Services (RCS) , gå till **Globaliseringsfunktioner** \> **Moms**.
2. Välj **Lägg till**, ange information om den nya funktionen och välj sedan **Skapa funktion**.
3. På fliken **Versioner**, välj funktionen och välj sedan **Redigera**.
4. På fliken **Allmänt** i fältet **Konfigurationsversion**, välj den anpassade momskonfigurationen och versionen.
5. I dialogrutan **Hantera kolumner**, markera rubrik- och radkolumnerna som du vill inkludera i din anpassade momsmått och välj sedan högerpil för att lägga till dem i listan **Valda kolumner**.
