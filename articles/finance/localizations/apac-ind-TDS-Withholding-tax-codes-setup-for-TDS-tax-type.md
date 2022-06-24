---
title: Ställ in källskattekoder för TDS-skattetypen
description: I den här artikeln beskrivs hur du konfigurerar skattekoder för skatteavdrag vid källan (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: fabe14b74c445434c37cb6ee79597d37affb162d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904395"
---
# <a name="set-up-withholding-tax-codes-for-the-tds-tax-type"></a>Ställ in källskattekoder för TDS-skattetypen

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs hur du konfigurerar skattekoder för skatteavdrag vid källan (TDS).

1. Gå till **Skatt \> Indirekt skatt \> Källskatt \> Källskattekoder**.

    [![Sidan Källskattekoder.](./media/apac-ind-TDS-17.png)](./media/apac-ind-TDS-17.png)

2. I åtgärdsfönstret väljer du **Ny** för att skapa en källskattekod för TDS och anger den information som krävs.
3. Under snabbfliken **Allmänt**, i fältet **Skattetyp**, väljer du **TDS** för att kategorisera skattekoder som en TDS-skattekod.
4. I fältet **Kvittningsperiod** väljer du TDS-kvittningsperioden för TDS-skattekoden.
5. I fältet **Huvudkonto** väljer du redovisningskontot som TDS-beloppet ska bokföras i.
6. I fältet **Kundreskontrakonto** väljer du det kundreskontrakonto som TDS-beloppet som dras av i försäljningstransaktioner ska bokföras i.

    Fältet **Ursprung** ställs automatiskt in på **Procentandel av bruttobelopp**, och värdet kan inte ändras.

    > [!NOTE]
    > Du kan inte ställa in ursprunget på **Procentandel av nettobelopp** för skattekoder av skattetypen TDS.

7. I fältet **Källskattekomponent** väljer du TDS-skattekomponenten för TDS-skattekoden.
8. I åtgärdsfönstret väljer du **Värden** för att öppna sidan **Källskattevärden**.
9. I fältet **Från-datum** anger du startdatum för TDS-värdet. I fältet **Till-datum** anger du slutdatum.

    > [!NOTE]
    > Fälten **Nedre gräns**, **Övre gräns** och **Exkludera %** är inte tillgängliga för skattekoder av skattetypen TDS.

10. I fältet **Värde** anger du procentandelen av TDS för TDS-skattekoden.
11. Stäng sidan **Källskattevärden** för att återgå till sidan **Källskattekoder**.

    > [!NOTE]
    > Knappen **Gränser** på sidan **Källskattekoder** är inte tillgänglig för skattekoder av skattetypen TDS.

12. Stäng sidan.
