---
title: Tröskelvärde och tröskelvärde för undantag
description: I det här avsnittet beskrivs tröskelvärden och undantagsgränser för skatteavdrag vid källa (TDS).
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
ms.openlocfilehash: 1bf0d3a01ede559d288581d3b58b3777d0e608dc
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023592"
---
# <a name="threshold-limit-and-exception-threshold-limit"></a>Tröskelvärde och tröskelvärde för undantag

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs tröskelvärden och undantagsgränser för skatteavdrag vid källa (TDS). TDS för fakturor och betalningar beräknas alltid med hänsyn till det tröskelvärde och den undantagströskel som definierats för TDS-skattekomponenterna på sidan **Källskattekomponenter**. TDS-skattekomponenterna kopplas till TDS-skattekoder, som är inkluderade i TDS-skattegrupperna. TDS-skattegrupperna kopplas till leverantörer och kunder för beräkning av TDS på fakturanivå eller betalningsnivå.

TDS beräknas om beloppet för en transaktion eller de ackumulerade transaktioner som bokförts med en specifik TDS-grupp för en leverantör överskrider den tröskelgräns som anges på sidan **Källskattekomponenter**. TDS beräknas inte förrän det ackumulerade transaktionsbeloppet överskrider den angivna tröskelgränsen.

Om en undantagströskelgräns anges tillsammans med tröskelvärdet för en TDS-komponent, beräknas TDS när ett specifikt transaktionsbelopp överskrider undantagströskeln även om det ackumulerade transaktionsbeloppet inte överskrider det angivna tröskelvärdet.

### <a name="example"></a>Exempel
En skattekomponent som kallas TDS ställs in och kopplas till den TDS-skattegrupp som kallas Leverantör. Tröskelvärdet har definierats som 50 000 och undantagströskeln har definierats som 20 000 för TDS-skattekomponenten. Leverantören för TDS-gruppen definieras som standardgrupp för TDS för leverantör 1.

En inköpsfaktura 001 bokförs för leverantör 1 för 10 000. TDS beräknas inte för fakturan eftersom fakturabeloppet inte har passerat tröskelvärdet eller undantagströskeln. En inköpsfaktura 002 bokförs för leverantör 1 för 25 000. TDS beräknas för fakturan eftersom fakturabeloppet har passerat undantagströskeln. En inköpsfaktura 003 bokförs för leverantör 1 för 20 000. TDS beräknas för fakturan eftersom det totala fakturabeloppet för de tre fakturor som skickas för leverantören har passerat tröskelvärdet. TDS beräknas på alla fakturor som har utfärdats för leverantören där TDS inte har beräknats tidigare. Därför beräknas TDS på 30 000, vilket är det totala fakturabeloppet på faktura 001 och 003.

Tröskelgränsen och undantagströskeln beaktas inte i TDS-beräkningen om kryssrutan **Förbigå tröskelvärde** har markerats för TDS-skattekoder i TDS-gruppen som är kopplad till transaktionen. Tröskelgränsen används inte i TDS-skattekoderna i TDS-gruppen som kryssrutan **Förbigå tröskelvärde** gäller för.

Om kryssrutan **Förbigå tröskelvärde** har markerats för en specifik TDS-grupp för några fakturor, men inte markerats för andra fakturor som skapades för en specifik leverantör/kund, kan det hända att beräkningen av TDS utan att förbigå tröskelgränsen för några fakturor sker baserat på det ackumulerade beloppet på alla fakturor som TDS inte har beräknats för tidigare.

Tröskelvärdet är till exempel 25 000. Följande fakturor skapas för leverantör A.

- Faktura 1 – 20 000 – (Kryssrutan **Förbigå tröskelvärde** har inte markerats): TDS har inte beräknats.

- Faktura 2 – 4 000 – (Kryssrutan **Förbigå tröskelvärde** har inte markerats): TDS har beräknats på 4 000.

- Faktura 2 – 3 000 – (Kryssrutan **Förbigå tröskelvärde** har inte markerats): TDS beräknas som det ackumulerade fakturabeloppet, det vill säga 27 000 (20 000 + 4 000 + 3 000) över tröskelvärdet. TDS beräknas på det ackumulerade beloppet för fakturor där TDS inte har beräknats tidigare, det vill säga på 23 000 (20 000 + 3 000).
