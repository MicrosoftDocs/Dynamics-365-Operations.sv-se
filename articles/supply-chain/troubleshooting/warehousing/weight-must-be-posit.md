---
title: Vikten måste vara positiv
description: Vikten måste vara positiv
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSContainerCloseDiag_canClose
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 27ec37e0c0644ff10ece4626d5c136bca3c52ef12f1c6de947afd03003a5368a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6776786"
---
# <a name="weight-must-be-positive"></a>Vikten måste vara positiv

Felkod: WeightMustBePositive

## <a name="symptoms"></a>Symtom

Systemet visar följande felmeddelande:

> Vikten måste vara positiv.

## <a name="cause"></a>Orsak

Fältet **Bruttovikt** ställs in på *0* (noll) eller ett negativt värde.

## <a name="resolution"></a>Upplösning

Om du vill ange en vikt gör du något av följande:

- Ange ett värde i fältet **Bruttovikt**. Välj sedan en enhet i listrutan.
- Välj **Hämta systemvikt** för att beräkna värdet för **Bruttovikt**.
