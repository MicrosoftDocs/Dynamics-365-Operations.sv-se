---
title: Beräkna TDS-fakturor med hjälp av inköpsorderformulär och försäljningsorderformulär
description: Det här ämnet visar en lista med stegen för beräkning av avdragen moms vid källan (TDS) på olika typer av fakturor.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: e7925206f3c060c6332de9d4972c8a7fb0066be2
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023588"
---
# <a name="calculate-tds-invoices-using-purchase-order-form-and-sales-order-form"></a>Beräkna TDS-fakturor med hjälp av inköpsorderformulär och försäljningsorderformulär

[!include [banner](../includes/banner.md)]

Det här ämnet visar en lista med stegen för beräkning för avdragen moms vid källan (TDS) på olika typer av fakturor med sidorna **Inköpsorder**, **Inköpsjournal**, **Ramavtal** och **Försäljningsorder**.

1. Skapa en inköpsorder, inköpsjournal, inköpsramavtal eller en försäljningsorder med den sida som visas. Ange den information som behövs.

2. Välj fliken **Inställningar** vilken typ av bedömare leverantören eller kunden är. Den här informationen visas i fältet **Typ av bedömare** under fältgruppen **Källskattegrupp**.

3. I fältet **TDS-grupp** visar eller modifierar du standard-TDS-gruppen som definierats för leverantören eller kunden.

   > [!NOTE]
   > Fältet **TCS-grupp** är inte tillgängligt när du väljer en TDS-grupp i fältet **TDS-grupp**. TDS beräknas endast om kryssrutan **Beräkna källskatt** har markerats för leverantören eller kunden på sidan **Alla leverantörer** eller **Alla kunder**.  

4. Skapa artikelrader på fliken **Rader** och ange den information som krävs.

5. Välj fliken **Inställningar** (radnivå) för att visa eller ändra TDS-gruppen som definierats på rubriknivå. TDS-gruppen visas i fältet **TDS-grupp**, som är under fältgruppen **Källskattegrupp**.

6. Välj fliken **Skatteinformation** och välj alternativa adresser som har konfigurerats för företagsnamnet som visas i fältet. Företagsnamnet visas i fältet **Namn**, som är under fältgruppen **Företagsinformation**. 

   TAN för det valda företagsnamnet visas i fältet **Skattekontonummer** (**TAN**), under fältgruppen **Källskatt**. 

7. Välj **Källskatt** för att öppna sidan **Temporära källskattetransaktioner**. Visa följande fält i det övre fönstret på sidan **Temporära källskattetransaktioner**.

   - **Total källskatt** - Total TDS beräknad för transaktionen för TDS-gruppen.

   - **Värde** – Den totala procentsatsen som används för att beräkna TDS för transaktionen. Den totala procentsatsen baseras på formeln som definieras för TDS-momskoder som är kopplade till TDS-gruppen.

   - **AJusterat totalt källskattebelopp** - Det totala justerade TDS-beloppet för alla momskoder i TDS-gruppen.

   - **TDS** – Om detta väljs kopplas en TDS-grupp till transaktionen.

Fälten under flikarna **Översikt**, **Allmänt** och **Justering** på sidan **Temporära källskattetransaktioner** visar det beräknade TDS-beloppet och justerad TDS-beloppinformation för varje TDS-momskod som är kopplad till TDS-gruppen.

8. Välj **Tröskel** för att öppna sidan **Tröskel**. Visa den tröskelgräns som har definierats för den TDS-momskomponent som är kopplad till en specifik TDS-momskod på den här sidan.

9. Välj **Formeldesigner** för att öppna sidan **Formeldesigner**. Visa formeln som definieras för en specifik TDS-momskod på den här sidan. 

10. Bokför fakturan. TDS-beloppet som beräknas på inköpsfakturor bokförs på leverantörsreskontrakontot och TDS-beloppet som beräknas på försäljningsfakturor bokförs på kundreskontrakontot som har definierats för varje TDS-momskod i TDS-gruppen. Leverantörsreskontrakontona och kundreskontrakontona för TDS-skattekoder definieras på sidan **Källskattekoder**.

11. Välj knappen **Fråga** **> Faktura > Bokförd källskatt** för att öppna sidan **Källskattetransaktioner**. Du kan visa den totala procentsatsen som används för att beräkna TDS för transaktionen i fältet **Värde**.

Fälten under flikarna **Översikt**, **Allmänt** och **Belopp** på sidan **Källskattetransaktioner** visar informationen för TDS som beräknats för transaktionen. Visa TDS-beräkningsinformation för varje TDS-momskod som är kopplad till TDS-gruppen.
