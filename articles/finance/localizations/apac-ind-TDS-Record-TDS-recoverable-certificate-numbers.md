---
title: Registrera återställningsbara certifikatnummer för TDS
description: I det här avsnittet beskrivs hur du använder sidan Återställningsbara certifikat för att registrera certifikatnummer och datum för TDS-certifikat (skatteavdrag vid källan) som har mottagits för en viss leverantör, kund eller redovisning.
author: kailiang
mms.date: 02/12/2021
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
ms.openlocfilehash: b501c331cccc6d030f36d0a13ba0a6a13c08c733
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023584"
---
# <a name="record-tds-recoverable-certificate-numbers"></a>Registrera återställningsbara certifikatnummer för TDS

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du använder sidan **Återställningsbara certifikat** för att registrera certifikatnummer och datum för TDS-certifikat (skatteavdrag vid källan) som har mottagits för en viss leverantör, kund eller redovisning. Om du vill uppdatera TDS-certifikatnummer och datum som har registrerats för TDS-transaktioner på den här sidan, använder du sidan **Uppdatera certifikat** (**Redovisning \> Periodisk \> Källskatt \> Uppdatera certifikat**). När du är klar med att uppdatera TDS-certifikatnummer stänger du dem.

Följ dessa steg om du vill registrera nummer och datum för TDS-certifikat.

1. Gå till **Skatt \> Indirekt skatt \> Källskatt \> Återställningsbara certifikat**.

    [![Sidan Återställningsbara certifikat](./media/apac-ind-TDS-49.png)](./media/apac-ind-TDS-49.png) 

2. På sidan **Återställningsbara certifikat**, i fältet **Skattetyp**, väljer du **TDS**.
3. Välj **Ny** för att skapa en post.
4. I fältet **Certifikatnummer** anger du numret på TDS-certifikatet.
5. I fältet **Kontotyp** väljer du den typ av konto som TDS-certifikatet tas emot för: **Leverantör**, **Kund** eller **Redovisning**.
6. I fältet **Konto** väljer du kontonumret för leverantör, kund eller redovisning, beroende på vilken kontotyp du har valt. I fältet **Namn** visas namnet på leverantören, kunden eller redovisningen.
7. I fältet **Certifikatbelopp** anger du beloppet för TDS-certifikatet.
8. I fältet **Datum** anger du certifikatdatumet för certifikatnumret.
9. Välj **Förfrågningar** för att öppna sidan **Certifikattransaktioner**, där du kan visa TDS-transaktioner som numret och datumet för TDS-certifikatet har uppdaterats för. Den här informationen kan uppdateras på sidan **Uppdatera certifikat** (**Skatt \> Deklarationer \> Källskatt \> Uppdatera certifikat**).

    På sidan **Uppdatera certifikat** visas följande information för varje TDS-transaktion:

    - **Datum** – Bokföringsdatum för TDS-transaktionen.
    - **Verifiering** – Verifieringsnumret för TDS-transaktionen.
    - **Källa** – Modulen där TDS-transaktionen skapades.
    - **Konto** – Kontonummer för leverantör, kund eller redovisning som TDS-transaktionen skapades för.
    - **Namn** – Namnet på kontot för leverantör, kund eller redovisning som TDS-transaktionen skapades för.
    - **Belopp** – Fakturabeloppet som TDS beräknades på.
    - **Skattebelopp** – TDS-skatten som har beräknats för transaktionen.
    - **Certifikatdatum** – TDS-certifikatdatumet som uppdaterades för TDS-transaktionen.
    - **Certifikatnummer** – TDS-certifikatnummer som uppdaterades för TDS-transaktionen.

10. På sidan **Återställningsbara certifikat** markerar du kryssrutan **Stängd** för att stänga TDS-certifikatnumret när du är klar med uppdateringen för TDS-transaktioner på sidan **Uppdatera certifikat**.

    För att markera kryssrutan **Stängd** för alla poster på sidan väljer du **Markera alla**.

    > [!NOTE]
    > TDS-certifikatnummer som kryssrutan **Stängd** har markerats för är inte tillgängliga på sidan **Uppdatera certifikat**.
