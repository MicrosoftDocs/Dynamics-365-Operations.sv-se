---
title: Konfigurara skattekomponenter för skattetypen TDS
description: I den här artikeln beskrivs hur du ställer in källskattekomponenter för skattetypen Skatteavdrag vid källa (TDS). Här förklaras också hur du definierar den tröskelgräns som används för att beräkna TDS för varje TDS-komponent.
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
ms.openlocfilehash: df2eb10ce9e372bb1e984f6ae1a2e889bbd90ad0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871169"
---
# <a name="set-up-tax-components-for-the-tds-tax-type"></a>Konfigurara skattekomponenter för skattetypen TDS

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs hur du ställer in källskattekomponenter för skattetypen Skatteavdrag vid källa (TDS). TDS-komponenterna är TDS, tilläggsavgift, PE-Cess och SHE Cess. I den här artikeln förklaras också hur du definierar den tröskel som används för att beräkna TDS för varje TDS-komponent. Du kan dessutom definiera ett undantagströskelvärde som används för att beräkna TDS för varje TDS-komponent.

Följ dessa steg för att ställa in TDS-komponenter.

1. Gå till **Skatt \> Konfiguration \> Källskatt \> Källskattekomponenter**.

    [![Sidan Källskattekomponenter.](./media/apac-ind-TDS-9.png)](./media/apac-ind-TDS-9.png)

2. I fältet **Skattetyp** väljer du **TDS** för att konfigurera källskattekomponenter för skattetypen TDS.
3. I åtgärdsfönstret, välj **Ny** för att skapa en rad.
4. I fältet **Källskattekomponenter** anger du ett namn på TDS-komponenten.
5. I fältet **Källskattekomponentgrupp** väljer du källskattekomponentgruppen TDS som TDS-komponenten ska kopplas till.
6. På snabbfliken **Allmänt** i fältet **Beskrivning** anger du en beskrivning för TDS-komponenten.
7. I åtgärdsfönstret väljer du **Tröskel** för att öppna sidan **Tröskel**, så att du kan definiera den tröskel som används för att beräkna TDS för TDS-komponenten.
8. Använd fälten **Från-datum** och **Till-datum** för att definiera perioden som tröskeln gäller.
9. Under snabbfliken **Allmänt**, i fältet **Tröskel**, anger du tröskelvärdet som används för att beräkna TDS för TDS-komponenten. Skatten dras av vid källan bara när det ackumulerade fakturabeloppet går över tröskelvärdet.

    Om t.ex. tröskelbeloppet är 10 000 beräknas TDS efter att det ackumulerade fakturabeloppet överstiger 10 000 (d.v.s. när det är 10 001 eller mer).

10. I fältet **Undantagströskel** anger du undantagströskelvärdet som används för att beräkna TDS för TDS-komponenten. Skatten på en fakturarad dras av vid källan bara när beloppet går över undantagströskelvärdet.

    Om undantagströskelbeloppet till exempel är 5 000, beräknas TDS på en specifik fakturarad om fakturaradsbeloppet överstiger 5 000 (med andra ord om det är 5 001 eller mer).

    [![Sidan Tröskel.](./media/apac-ind-TDS-10.png)](./media/apac-ind-TDS-10.png)

    > [!NOTE]
    > Undantagströskeln måste vara mindre än eller lika med tröskelbeloppet.
    >
    > Skatten dras av för en transaktion om transaktionsbeloppet går över undantagströskeln, även om det ackumulerade fakturabeloppet inte går över tröskelvärdet som har angetts i fältet **Tröskel**.

11. Stäng sidan **Tröskel** för att återgå till sidan **Källskattekomponenter**.
12. I åtgärdsfönstret väljer du **Kopiera** för att öppna dialogrutan **Kopiera källskattekomponenter**, så att du kan kopiera TDS-komponenter som konfigurerades för en TDS-komponentgrupp till en annan TDS-komponentgrupp.
13. I fältet **Från** väljer du den TDS-komponentgrupp som TDS-komponenterna ska kopieras från. I fältet **Till** väljer du den källskattekomponentgrupp som TDS-komponenterna ska kopieras till.

    > [!NOTE]
    > Vanliga TDS-komponenter som är kopplade till båda TDS-komponentgrupperna kopieras inte.

14. Välj **OK** för att kopiera och skapa TDS-komponenter för den andra TDS-komponentgruppen på sidan **Källskattekomponenter**.

    [![Dialogrutan Kopiera källskattekomponenter.](./media/apac-ind-TDS-11.png)](./media/apac-ind-TDS-11.png)

15. Stäng sidan.
