---
title: Valt formelnummer som inte godkänts för en batchorder
description: När du försöker bekräfta en planerad order visas ett felmeddelande där det står att det valda formelnumret inte är godkänt för en batchorder.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4f993c92ca0a2f8f79e4b0e0eda43904529163f8
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294178"
---
# <a name="selected-formula-number-isnt-approved-for-a-batch-order"></a>Valt formelnummer som inte godkänts för en batchorder

Felkod: PRO2614

## <a name="symptoms"></a>Symtom

När du har bekräftat planerade order visas följande felmeddelande:

> Det valda formelnumret är inte godkänt för en batchorder.

## <a name="cause"></a>Orsak

Systemet validerar bekräftad operation för att se till att ett godkänt recept är tillgängligt för den aktiva artikeln. Du måste troligen godkänna formel.

## <a name="resolution"></a>Lösning

Följ anvisningarna nedan om du vill godkänna en formel.

1. Gå till **Produktinformationshantering \> Strukturlistor och formler \> Formler**.
1. Välj relevant formel.
1. I Åtgärdsfönstret, på fliken **formel**, i gruppen **underhåll**, markerar du **godkänn formel**.
1. Välj en godkännare i dialogrutan **Godkänn strukturlista** eller recept och välj **OK**.
