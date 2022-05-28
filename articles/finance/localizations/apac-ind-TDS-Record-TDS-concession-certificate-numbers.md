---
title: Registrera koncessionscertifikatnummer för TDS
description: I det här avsnittet beskrivs hur du registrerar koncessionscertifikatnumren för skatteavdrag vid källan (TDS) som har utfärdats till leverantörer.
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
ms.openlocfilehash: 994ddbb4666c326d237d53d529ba126f42d48595
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727157"
---
# <a name="record-tds-concession-certificate-numbers"></a>Registrera koncessionscertifikatnummer för TDS

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du registrerar koncessionscertifikatnumren för skatteavdrag vid källan (TDS) som har utfärdats till leverantörer.

1. Gå till **Skatt \> Indirekta skatter \> Källskatt \> Källskattekoncessioner**.
2. I fältet **Skattetyp** väljer du **TDS** för att registrera koncessionscertifikat för TDS-skattetypen.
3. På fliken **Översikt** väljer du **Alt+N** för att skapa en rad.

    [![Rubrik för den nya raden.](./media/apac-ind-TDS-34.png)](./media/apac-ind-TDS-34.png)

4. I fältet **Källskattekod** väljer du den TDS-skattekod som leverantörens koncessionscertifikat utfärdas för. I fältet **Namn på källskattekod** visas namnet på TDS-skattekoden.
5. I fälten **Från datum** och **Till datum** definierar du giltighetsperioden för det koncessionscertifikat som använder TDS-skattekoden för att beräkna TDS för leverantören på koncessionsbasis.
6. I fältet **Anmärkningar** anger du eventuella anmärkningar.
7. I fältet **Avsnitt** anger du den juridiska avsnittskod som TDS-koncessionscertifikatet visas under.

    Om avsnittskoden är 197 visas värdet "A" i kolumnen "Orsak till icke-avdrag/lägre avdrag" i formulär 26Q och kolumnen "Orsak till icke-avdrag/lägre avdrag/bruttoavdrag (i tillämpliga fall)", i formulär 27Q. Om avsnittskoden är 197A visas värdet "B" på båda ställena.

8. Markera snabbfliken **Certifikat** om du vill registrera TDS-koncessionscertifikatnummer för leverantörer.
9. I fältet **Leverantörskonto** väljer du det leverantörskonto som TDS-koncessionscertifikatet utfärdas för.
10. I fälten **Från datum** och **Till datum** definierar du giltighetsperioden för TDS-koncessionscertifikaten.

    Beräkningen av TDS på koncessionsbasis baseras på perioden när certifikat skapas för leverantören.

11. I fältet **Certifikat** anger du numret på TDS-koncessionscertifikatet.

    [![Snabbfliken Certifikat.](./media/apac-ind-TDS-33.png)](./media/apac-ind-TDS-33.png)

12. Stäng sidan.
