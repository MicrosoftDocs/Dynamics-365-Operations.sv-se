---
title: Ställa in mappning för kolumnerna för försäljningsorderns status
description: I den här artikeln beskrivs hur du ställer in kolumnerna för försäljningsorderstatus för dubbelriktad skrivning.
author: dasani-madipalli
ms.date: 06/25/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: damadipa
ms.search.validFrom: 2020-06-25
ms.openlocfilehash: 2035985f16b5972e02f1ed60c6f02d306217f3be
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288897"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-columns"></a>Ställa in mappning för kolumnerna för försäljningsorderns status

[!include [banner](../../includes/banner.md)]

De kolumner som anger försäljningsorderstatus har olika uppräkningsvärden i Microsoft Dynamics 365 Supply Chain Management och Dynamics 365 Sales. Det krävs ytterligare inställningar för att mappa dessa kolumner i dubbelriktad skrivning.

## <a name="columns-in-supply-chain-management"></a>kolumner i Supply Chain Management

I Supply Chain Management visar två kolumner status för försäljningsordern. De kolumner som du måste mappa är **status** och **dokumentstatus**.

**Status** uppräkningen anger den övergripande statusen för ordern. Denna status visas i orderrubriken.

**Status** uppräkningen har följande värden:

- Öppen order
- Levererat
- Fakturerat
- Avbröts

**Dokumentstatus** uppräkningen anger det senaste dokument som skapades för ordern. Om t.ex. en order är bekräftad är dokumentet en bekräftelse på försäljningsorder. Om en försäljningsorder är delvis fakturerad och den återstående raden bekräftas, kommer dokumentstatusen att ha kvar **faktura**, eftersom fakturan genereras senare i processen.

**Dokumentstatus** uppräkningen har följande värden:

- Bekräftelse
- Plocklista
- Följesedel
- Faktura

## <a name="columns-in-sales"></a>kolumner i Sales

I Sales anger två kolumner status för ordern. De kolumner som du måste mappa är **status** och **Bearbetningsstatus**.

**Status** uppräkningen anger den övergripande statusen för ordern. Det har följande värden:

- Aktiva
- Skickade
- Uppfyllt
- Fakturerat
- Avbröts

Uppräkningen av **bearbetningsstatus** introducerades så att statusen kan mappas mer exakt med Supply Chain Management.

Följande tabell visar en mappning av **bearbetningsstatus** i Supply Chain Management.

| Bearbetningsstatus   | Status i Supply Chain Management | Dokumentstatus i Supply Chain Management |
|---------------------|-----------------------------------|--------------------------------------------|
| Aktiva              | Öppen order                        | None                                       |
| Bekräftat           | Öppen order                        | Bekräftelse                               |
| Plockad              | Öppen order                        | Plocklista                               |
| Delvis levererad | Öppen order                        | Följesedel                               |
| Levererat           | Levererat                         | Följesedel                               |
| Delvis fakturerad  | Levererat                         | Faktura                                    |
| Fakturerat            | Fakturerat                          | Faktura                                    |
| Avbröts           | Avbröts                         | Inte aktuellt                             |

Följande tabell visar en mappning av **bearbetningsstatus** mellan Sales och Supply Chain Management.

| Bearbetningsstatus   | Status i Sales | Status i Supply Chain Management |
|---------------------|-----------------|-----------------------------------|
| Aktiva              | Aktiva          | Öppen order                        |
| Bekräftat           | Skickade       | Öppen order                        |
| Plockad              | Skickade       | Öppen order                        |
| Delvis levererad | Aktiva          | Öppen order                        |
| Delvis fakturerad  | Aktiva          | Öppen order                        |
| Delvis fakturerad  | Uppfyllt       | Levererat                         |
| Fakturerat            | Fakturerat        | Fakturerat                          |
| Avbröts           | Avbröts       | Avbröts                         |

## <a name="setup"></a>Ställ in

Om du vill ställa in mappningen för kolumner för försäljningsorderstatus måste du aktivera attributen **IsSOPIntegreringEnabled** och **isIntegreringUser**.

Så här aktiverar du attribut **IsSOPIntegreringEnabled** följ dessa steg.

1. I en webbläsare går du till `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`. Ersätt **\<test-name\>** med företagets länk till Sales.
2. På den sida som är öppnad, sök efter **organizationid** och anteckna värdet.

    ![Sök efter organizationid.](media/sales-map-orgid.png)

3. Öppna webbläsarkonsolen i Sales och kör följande skript. Använd värdet **organizationid** från steg 2.

    ```javascript
    Xrm.WebApi.updateRecord("organization",
    "d9a7c5f7-acbf-4aa9-86e8-a891c43f748c", {"issopintegrationenabled" :
    true}).then(
        function success(result) {
            console.log("Account updated");
            // perform operations on row update
        },
        function (error) {
            console.log(error.message);
            // handle error conditions
        }
    );
    ```

    ![JavaScript-kod i webbläsarkonsolen.](media/sales-map-script.png)

4. Kontrollera att **IsSOPIntegreringEnabled** är inställt på **true**. Använd URL från steg 1 för att kontrollera värdet.

    ![Ange IsSOPIntegreringEnabled till "true".](media/sales-map-integration-enabled.png)

Så här aktiverar du attribut **isIntegreringUser** följ dessa steg.

1. I Sales, gå till **Inställning \> Anpassning \> Anpassa systemet**, välj **Användartabell** och öppna sedan **Formulär \> Användare**.

    ![Öppna användarformuläret.](media/sales-map-user.png)

2. I Tillgängliga fält, hitta **Användarläge för integrering** och dubbelklicka på den för att lägga till den i formuläret. Spara ändringarna.

    ![Lägga till kolumnen Användarläge för integrering i formuläret.](media/sales-map-field-explorer.png)

3. I Sales, gå till **inställning \> säkerhet \> användare** och ändra vyn från **aktiverade användare** till **programanvändare**.

    ![Ändra visningen från Aktiverade användare till Programanvändare.](media/sales-map-enabled-users.png)

4. Välj de två posterna för **DualWrite IntegreringUser**.

    ![Lista över programanvändare.](media/sales-map-user-mode.png)

5. Ändra värdet för kolumnen **användarläge för integrering** till **Ja**.

    ![Ändra värdet för kolumnen Användarläge för integrering.](media/sales-map-user-mode-yes.png)

Dina försäljningsorder är nu mappade.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
