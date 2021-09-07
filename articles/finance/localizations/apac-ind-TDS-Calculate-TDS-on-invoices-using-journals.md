---
title: Beräkna TDS på fakturor med journaler
description: Det här ämnet visar en lista med stegen för beräkning av avdragen moms vid källan (TDS) på journaler.
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
ms.openlocfilehash: fde81efed6b8a72e2149056f0196e4f9d60e59f2
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345529"
---
# <a name="calculate-tds-on-invoices-using-journals"></a>Beräkna TDS på fakturor med journaler

[!include [banner](../includes/banner.md)]

Det här ämnet visar en lista med stegen för beräkning av avdragen moms vid källan (TDS) på journaler.

Börja med att öppna sidan **Allmänna journaler** (**Redovisning > Journalposter > Allmänna journaler**).

[![Allmänna journaler.](./media/apac-ind-TDS-57.png)](./media/apac-ind-TDS-57.png)

1. Skapa journalrader med hjälp av journalformulären som visas i tabellen. Välj kontotyp och motkontotyp och ange transaktionsbeloppet. 

   > [!NOTE]
   > På sidan **Journal för fakturagodkännande** väljer du **Hitta verifikationer** och välj fakturor att beräkna TDS på. Visa fakturor som skapats på sidan **Fakturaregister** eller sidan **Hitta verifikationer**.  

2. Under fliken **Allmänt** på sidan **Journalverifikation** visar eller modifierar du standard-TDS-gruppen som definierats för leverantören eller kunden i fältet **TDS-grupp**. TDS-beloppet som beräknas på journalrader baseras på formeln som definierats för TDS-momskoderna som listas i fältet **TDS-grupp**. 

   > [!NOTE]
   > Fältet **Källskattegrupp** och fältet **TCS-grupp** blir otillgängligt när du väljer en TDS-grupp i fältet **TDS-grupp**. Fältet **Källskattegrupp** är endast tillgängligt på sidan **Allmän journal**. TDS beräknas endast om kryssrutan **Beräkna källskatt** har markerats för leverantören eller kunden på sidan **Alla leverantörer** eller **Alla kunder**.   

3. Välj fliken **Skatteinformation**. Välj alternativa adresser för ett företag som har konfigurerats för företaget i fältet, om så krävs. Du kan visa företagsnamnet visas i fältet **Namn**, som är under fältgruppen **Företagsinformation**. 

4. Visa leverantörens eller kundens bedömningskategori i fältet **Typ av bedömare**, som är under fältgruppen **Källskatt**. I fältet **Skattekontonummer** (**TAN**) visas TAN för det företagsnamn som visas.  

5. Välj **Källskatt** i menyn **Källskatt** för att öppna sidan **Temporära källskattetransaktioner**. Följande fält visas i det övre fönstret på sidan **Temporära källskattetransaktioner**.

   - **Total källskattebelopp** - Total TDS beräknad för transaktionen för TDS-gruppen.

   - **Värde** – Den totala procentsatsen som används för att beräkna TDS för transaktionen. Den totala procentsatsen baseras på formeln som definieras för TDS-momskoder som är kopplade till TDS-gruppen.

   - **AJusterat totalt källskattebelopp** - Det totala justerade TDS-beloppet för alla momskoder i TDS-gruppen.

   - **TDS** – Om detta väljs kopplas en TDS-grupp till transaktionen.

  Fälten under flikarna **Översikt**, **Allmänt** och **Justering** på sidan **Temporära källskattetransaktioner** visar det beräknade TDS-beloppet och justerad TDS-beloppinformation för varje TDS-momskod som är kopplad till TDS-gruppen.

6. Välj **Tröskel** för att öppna sidan **Tröskel**. Visa den tröskelgräns och det undantag som har definierats för den TDS-momskomponent som är kopplad till en specifik TDS-momskod på den här sidan.

   Välj **Formeldesigner** för att öppna formuläret **Formeldesigner**. Visa formeln som definieras för en specifik TDS-momskod på den här sidan. Stäng sidorna **Formeldesigner** och **Temporära källskattetransaktioner** för att återgå till sidan **Journalverifikation**.

8. Ange andra uppgifter som behövs. Validera och bokför journalen. Det TDS-belopp som beräknas på inköpsfakturor bokförs på leverantörsreskontrakontot. Det TDS-belopp som beräknas på försäljningsfakturor bokförs på det kundreskontrakonto som har definierats för varje TDS-momskod i TDS-gruppen. Leverantörsreskontrakontona och kundreskontrakontona för TDS-skattekoder definieras på sidan **Källskattekoder**.

9. Välj **Bokförd källskatt** för att öppna sidan **Källskattetransaktioner**. I fältet **Värde** visas den totala procentsats som användes för att beräkna TDS för transaktionen.

   Fälten under flikarna **Översikt**, **Allmänt** och **Belopp** på sidan Källskattetransaktioner visar det beräknade TDS-beloppet och justerad TDS-beloppinformation för varje TDS-momskod som är kopplad till TDS-gruppen.
