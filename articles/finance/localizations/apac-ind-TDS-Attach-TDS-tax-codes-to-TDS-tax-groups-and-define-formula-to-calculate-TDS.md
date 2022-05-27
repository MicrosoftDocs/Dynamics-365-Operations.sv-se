---
title: Koppla TDS-momskoder till TDS-momsgrupper och definiera formeln för att beräkna TDS
description: I det här avsnittet beskrivs hur du ställer in TDS-momsgrupper (Tax Deducted at Source) och kopplar TDS-momskoder till TDS-momsgrupper. Om du vill beräkna TDS för en TDS-momsgrupp måste du definiera formeln för TDS-momskoder som är kopplade till den.
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
ms.openlocfilehash: f1326f95c297887213ecfb572a2437867d964925
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2022
ms.locfileid: "8711248"
---
# <a name="attach-tds-tax-codes-to-tds-tax-groups-and-define-the-formula-for-calculating-tds"></a>Koppla TDS-momskoder till TDS-momsgrupper och definiera formeln för att beräkna TDS

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du ställer in TDS-momsgrupper (Tax Deducted at Source) och kopplar TDS-momskoder till TDS-momsgrupper. Om du vill beräkna TDS för en TDS-momsgrupp måste du definiera formeln för TDS-momskoder som är kopplade till den.

Följ dessa steg om du vill ställa in en TDS-momsgrupp, koppla TDS-momskoder till den och definiera formeln för beräkning av TDS.

1. Gå till **Skatt \> Indirekta skatter \> Källskatt \> Källskattegrupper**.

    [![Sidan Källskattegrupper.](./media/apac-ind-TDS-29.png)](./media/apac-ind-TDS-29.png)

2. I åtgärdsfönstret väljer du **Ny** för att skapa en källskattegrupp för TDS och anger den information som krävs.
3. I fältet **Momstyp**, välj **TDS**.
4. På snabbfliken **Konfigurera**, klicka på **Lägg till** för att skapa en rad.
5. I fältet **Källskattekod** väljer du TDS-skattekoden för TDS-skattegruppen. Fältet **Namn på källskatt** visar namnet på TDS-skattekoden, och fältet **Värde** visar värdet.
6. Om du vill ignorera det tröskelvärde och undantagströskelvärde som har definierats för TDS-momskomponenten som är kopplad till TDS-momskoden i TDS-transaktioner markerar du kryssrutan **Förbigå tröskelvärde**.
7. För att förhindra momsgruppen från att beräknas i transaktioner markerar du kryssrutan **Undantagen**.
8. I åtgärdsfönstret väljer du **Designer** för att öppna formeldesignern, så att du kan definiera formeln för beräkning av TDS för TDS-momsgruppen. På sidan **Designer** visar fliken **Skatter** TDS-momskoder som har valts för TDS-momsgruppen.

    [![Designersida.](./media/apac-ind-TDS-30.png)](./media/apac-ind-TDS-30.png)

9. På fliken **Beräkning** väljer du **Alt+N** för att skapa en rad. Fältet **ID** visar det automatiskt genererade prioritets-ID för TDS-beräkning.
10. I fältet **Momskod** väljer du TDS-momskoden som formeln ska definieras för. Alla TDS-momskoder som har valts för TDS-momsgruppen går att välja i det här fältet.
11. I fältet **Momsunderlag** väljer du bas för beräkning av TDS:

    - **Bruttobelopp** – Beräkna TDS baserat på bruttotransaktionsbeloppet (det vill säga fakturabeloppet) med hjälp av beräkningsuttrycket som definieras för momskoden.
    - **Exkl. bruttobelopp** – Beräkna TDS baserat på det beräkningsuttryck som är definierat för momskoden.

    > [!NOTE]
    > Fältet **Momsunderlag** kan inte ställas in på **Exkl. bruttobelopp** för TDS-momskoden med prioritets-ID **1**.

12. TDS-beräkningen baseras på formeln som definieras i fältet **Beräkningsuttryck** för varje momskod som är kopplad till TDS-momsgruppen. Välj plustecknet (+), minustecknet (-), multiplikationstecknet (\*) eller divisionstecknet (/) för att ange beräkningsuttrycket för den valda TDS-momskoden i fältet **Beräkningsuttryck**.

    > [!NOTE]
    > Inget beräkningsuttryck kan definieras för TDS-momskoden som har prioritets-ID **1**.

13. Om du vill definiera beräkningsuttrycket för TDS-momskoden i fältet **Beräkningsuttryck** lägger du till TDS-momskoder som är tillgängliga under fliken **Skatter**. Om du vill lägga till TDS-momskoder i fältet **Beräkningsuttryck** kan du använda någon av följande metoder:

    - Dra den nödvändiga momskoden från fliken **Skatter** till fältet **Beräkningsuttryck**.
    - Dubbelklicka på momskoden på fliken **Skatter**.
    - Tryck på och håll inne (eller högerklicka) momskoden på fliken **Skatter** och välj sedan **Lägg till momskod**.

    > [!NOTE]
    > Infoga ett beräkningsuttryck före varje TDS-momskod. De TDS-momskoder som har lagts till i beräkningsuttrycket visas inom hakparenteser (\[...\]).

14. Om du vill rensa beräkningsuttrycket som har definierats för en momskod i fältet **Beräkningsuttryck** väljer du knappen **C**.
15. Om du vill ta bort en post på fliken **Beräkning** väljer du **Ta bort**.
16. Stäng sidan.
