---
title: TDS-beräkning på fakturor från sidan Fritextfaktura
description: I den här artikeln beskrivs hur du beräknar skatteavdrag vid källan (TDS) på fakturor med hjälp av sidan Fritextfaktura.
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
ms.openlocfilehash: b1cf0f5366315884e75a6fee25b88a3aac7d62de
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856623"
---
# <a name="tds-calculation-on-invoices-from-the-free-text-invoice-page"></a>TDS-beräkning på fakturor från sidan Fritextfaktura

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs hur du beräknar skatteavdrag vid källan (TDS) på fakturor med hjälp av sidan **Fritextfaktura**.

1. Gå till **Kundreskontra \> Fakturor \> Alla fritextfakturor**.

    [![Sidan Fritextfakturor.](./media/apac-ind-TDS-57-1.png)](./media/apac-ind-TDS-57-1.png)

2. Välj **Ny** för att skapa en fritextfaktura och ange den information som krävs.
3. Välj fliken **Faktura**. I avsnittet **Källskattegrupp** visar fältet **Typ av bedömare** kundens typ av bedömningskategori.
4. I fältet **TDS-grupp** granskar eller ändrar du standard-TDS-gruppen som definierats för kunden.

    > [!NOTE]
    > När du väljer ett värde i fältet **TDS-grupp** blir fältet **TCS-grupp** otillgängligt. TDS beräknas endast om alternativet **Beräkna källskatt** har ställts in på **Ja** för kunden på sidan **Alla kunder**.

5. Under fliken **Skatteinformation**, i avsnittet **Företagsinformation**, i fältet **Namn**, väljer du företagsnamnet för en alternativ adress som har konfigurerats för företaget.

    I avsnittet **Källskatt** visar fältet **Skattekontonummer (TAN)** skattekontonumret (TAN) för det valda företaget.

6. Under fliken **Fakturarader** skapar du fakturarader och anger den information som krävs.

    I avsnittet **Källskattegrupp** visar fältet **Skattekontonummer (TAN)** TAN, och fältet **TDS-grupp** visar TDS-gruppen.

7. Välj **Källskatt** för att öppna sidan **Temporära källskattetransaktioner**. Den övre delen av den här sidan har följande fält:

    - **Totalt källskattebelopp** – Total TDS beräknad för transaktionen för TDS-gruppen.
    - **Värde** – Den totala procentsatsen som används för att beräkna TDS för transaktionen. Den totala procentsatsen baseras på formeln som definieras för TDS-skattekoder som är kopplade till TDS-gruppen.
    - **Justerat totalt källskattebelopp** – Det totala justerade TDS-beloppet för alla momskoder i TDS-gruppen.
    - **TDS** – En markerad kryssruta anger att en TDS-grupp är kopplad till transaktionen.

    Fälten under flikarna **Översikt**, **Allmänt** och **Justering** visar det beräknade TDS-beloppet och information om justerat TDS-belopp för varje TDS-skattekod som är kopplad till TDS-gruppen.

8. Välj **Tröskel** för att öppna sidan **Tröskel**, där du kan granska tröskelgränsen som har definierats för TDS-skattekomponenten som är kopplad till en specifik TDS-skattekod.
9. Välj **Formeldesigner** för att öppna sidan **Formeldesigner**, där du kan granska formeln som definierats för en specifik TDS-skattekod.
10. Bokför fritextfakturan. Det TDS-belopp som beräknas på fritextfakturor bokförs på det kundreskontrakonto som har definierats för varje TDS-momskod i TDS-gruppen. Kundreskontrakontona för TDS-skattekoder definieras på sidan **Källskattekoder**.
11. Välj **Bokförd källskatt** för att öppna sidan **Källskattetransaktioner**. I fältet **Värde** visas den totala procentsatsen som användes för att beräkna TDS för transaktionen.

    Fälten under flikarna **Översikt**, **Allmänt** och **Belopp** visar TDS-beloppen som beräknats på fakturaraderna.

12. Granska TDS-beräkningsinformation för varje TDS-skattekod som är kopplad till TDS-gruppen.
