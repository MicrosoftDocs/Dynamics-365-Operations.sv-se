---
title: Efterdaterade checkar
description: Det här avsnittet innehåller information om stöd för efterdaterade checkar i Microsoft Dynamics 365 Finance. Postdaterade checkar är checkar som har utfärdats för att skapa och ta emot betalningar vid ett framtida datum. Därför kan checken inte lösas in förrän på angivet datum.
author: ShylaThompson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPostDatedChecks, CustPostDatedChecks
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 21741
ms.assetid: 4eb7c7da-1e6b-4d35-9f41-373b66103229
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 38ee6c5b3d258c313a2066b388a83330bf696d39
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179991"
---
# <a name="postdated-checks"></a>Efterdaterade checkar

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om stöd för efterdaterade checkar. Postdaterade checkar är checkar som har utfärdats för att skapa och ta emot betalningar vid ett framtida datum. Därför kan checken inte lösas in förrän på angivet datum.

Dynamics 365 Finance stöder den fullständiga cykeln för efterdaterade checkar in både Leverantörsreskontra och Kundreskontra, enligt följande tabell.
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Scenario</th>
<th>Detaljer</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Ställ in efterdaterade checkar</td>
<td>Du måste ställa in en ny betalningsmetod och ange betalningsrutin för clearingkonton för betalda checkar, mottagna checkar och källskatt.</td>
</tr>
<tr class="even">
<td>Registrera och bokför en efterdaterad check för en leverantör</td>
<td>Registrera information om en efterdaterad check som du utfärdar till en leverantör. När betalningen bokförs känns leverantörsskulden igen, men bankkontot krediteras inte ännu. I stället används ett clearingkonto för detta ändamål. </td>
</tr>
<tr class="odd">
<td>Registrera och bokför en efterdaterad check för en kund</td>
<td>Registrera information om en efterdaterad check som tas emot från en kund. När betalningen bokförs krediteras kundfordringen, men bankkontot debiteras inte ännu. I stället används ett clearingkonto för detta ändamål.</td>
</tr>
<tr class="even">
<td>Registrera och bokför ett utbyte av en efterdaterad för en kund eller en leverantör</td>
<td>
Om din ursprungliga check till en leverantör eller från en kund förloras eller skadas kan du utfärda en efterdaterad check som substitut. När du registrerar informationen om checken ska du ange en referens till den ursprungliga checken och indikera att den nya checken ersätter den ursprungliga. Du kan även bokföra utbyteschecken.</td>
</tr>
<tr class="odd">
<td>Överför en efterdaterad kundcheck till en leverantör</td>
<td>När du får en efterdaterad check från en kund kan du överföra den till en leverantör som betalning.</td>
</tr>
<tr class="even">
<td>Betala en postdaterad check för en kund eller leverantör</td>
<td>Kvitta en efterdaterad check som har bokförts på ett interimskonto för en kund eller leverantör när checken har förfallit. När checken kvittad har banken slutligen debiterats eller krediterats mot clearingkontot som användes tidigare.</td>
</tr>
<tr class="odd">
<td>Annullera en efterdaterad check för en leverantör</td>
<td>Du kan avbryta en bokförd efterdaterad check i sådana fall: - Checken returneras av banken.
- Checken har tillämpats på fel faktura.
- En kontantbetalning görs mot checken.
  </td>
  </tr>
  <tr class="even">
  <td>Stoppa betalning för en efterdaterad check</td>
  <td>Du kan stoppa en efterdaterad checkbetalning som utfärdades till en leverantör av orsaker såsom otillräckliga medel, ändringar av villkoren för avtalet med leverantören, leverans av defekta varor från leverantören eller returnering av varor till leverantören. Du kan enbart stoppa betalning på checkar som inte har reglerats.</td>
  </tr>
  </tbody>
  </table>



Mer information finns i följande avsnitt:

[Ställ in efterdaterade checkar](tasks/set-up-postdated-checks.md)

[Registrera och bokför en efterdaterad check för en kund](tasks/register-post-postdated-check-customer.md)

[Kvitta en efterdaterad check från en kund](tasks/settle-postdated-check-customer.md)

[Registrera och bokför en efterdaterad check för en leverantör](tasks/register-post-postdated-check-vendor.md) 

[Kvitta en efterdaterad check för en leverantör](tasks/settle-postdated-check-vendor.md)



