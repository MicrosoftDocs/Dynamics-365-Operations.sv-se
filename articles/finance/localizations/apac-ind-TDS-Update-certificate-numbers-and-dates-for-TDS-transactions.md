---
title: Uppdatera certifikatnummer och datum för TDS-transaktioner
description: I det här avsnittet beskrivs hur du uppdaterar återställningsbara certifikatnummer och datum som registrerades för leverantörs-, kund- eller redovisningskonton för skatteavdrag vid källan (TDS).
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
ms.openlocfilehash: da835306e523129fb667153ff6a5fbe574f2769649639595c90af603f1258e4a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6758009"
---
# <a name="update-certificate-numbers-and-dates-for-tds-transactions"></a>Uppdatera certifikatnummer och datum för TDS-transaktioner

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du uppdaterar återställningsbara certifikatnummer och datum som registrerades för leverantörs-, kund- eller redovisningskonton för skatteavdrag vid källan (TDS). Du kan visa certifikat för TDS-transaktioner på sidan **Återställningsbara certifikat**. Du kan uppdatera certifikaten genom sidan **Uppdatera certifikat**.

Följ dessa steg om du vill uppdatera certifikatnummer och datum för TDS-transaktioner.

1. Gå till **Skatt \> Deklarationer \> Källskatt \> Uppdatera certifikat**.

    [![Sidan Uppdatera certifikat.](./media/apac-ind-TDS-45.png)](./media/apac-ind-TDS-45.png)

2. På sidan **Uppdatera certifikat**, i avsnittet **Välj**, i fältet **Skattetyp**, väljer du **TDS**.
3. I fältet **Certifikatnummer** väljer du kundens eller leverantörens TDS-certifikatnummer.

    > [!NOTE]
    > I fältet **Certifikatnummer** visas endast TDS-certifikatnummer som kryssrutan **Stängt** är avmarkerad för på sidan **Återställningsbara certifikat**.

    I fältet **Certifikat** visas certifikatdatumet. I fältet **Kontotyp** visas typen av konto som TDS-certifikatnumret tas emot för, och i fältet **Namn** visas namnet på kontot.

5. I fälten **Från-datum** och **Till-datum** väljer du start- och slutdatum för perioden som TDS-transaktioner ska visas för.
6. Välj **Visa data** för att visa TDS-transaktioner som bokfördes under den valda perioden.

    Under fliken **Översikt** visar rutnätet i det övre fönstret följande information om varje TDS-transaktion som bokfördes för leverantören eller kunden under den valda perioden:

    - **Verifiering** – Verifieringsnumret för TDS-transaktionen.
    - **Datum** – Datum för TDS-transaktionen.
    - **Belopp** – Fakturabeloppet som TDS beräknades på.
    - **Skattebelopp** – TDS-skatten som har beräknats för transaktionen.

7. Om du vill flytta specifika TDS-transaktioner från det övre rutnätet till det nedre rutnätet markerar du transaktionerna och väljer **Inkludera**. Du kan också välja **Inkludera alla** om du vill flytta alla TDS-transaktioner från det övre rutnätet till det nedre rutnätet.

    Om du vill flytta specifika TDS-transaktioner eller alla TDS-transaktioner från det nedre rutnätet till det övre rutnätet använder du knappen **Exkludera** eller **Exkludera alla**.

8. Välj **Uppdatera** för att uppdatera fälten **Certifikatnummer** och **Certifikatdatum** för TDS-transaktioner i det nedre rutnätet.
10. Gå till **Skatt \> Indirekt skatt \> Källskatt \> Återställningsbart certifikat** och välj **Förfrågan** för att visa de uppdaterade transaktionsraderna som har nya certifikatnummer på sidan **Certifikattransaktioner**.

    [![Sidan Certifikattransaktioner.](./media/apac-ind-TDS-46.png)](./media/apac-ind-TDS-46.png)
