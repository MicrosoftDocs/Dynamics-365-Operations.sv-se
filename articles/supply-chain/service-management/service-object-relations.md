---
title: Serviceobjektrelationer
description: Du kan skapa serviceobjektrelationer mellan ett serviceobjekt och ett serviceavtal eller en serviceorder.
author: sorenva
ms.date: 02/21/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceObjectRelation
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 831db29589826904666049edbc8be0c38e1d02a5
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8676647"
---
# <a name="service-object-relations"></a>Serviceobjektrelationer 

[!include [banner](../includes/banner.md)]

Du kan skapa serviceobjektrelationer mellan ett serviceobjekt och ett serviceavtal eller en serviceorder. När du skapar en relation kopplar du serviceobjektet till serviceavtalet eller serviceordern.

Efter att relationen är skapad kan du koppla serviceobjektet till alla rader i serviceavtalet eller serviceordern.

## <a name="template-boms"></a>Strukturlistemallar

Du kan även ange en strukturlistemall för objektrelationen. Strukturlistemallen är en strukturlista för det objekt på vilket tjänsten utförs. Om du ersätter en komponentdel av serviceobjektet under ett servicebesök kan du registrera denna ändring i servicestrukturlistan genom att använda formuläret för serviceobjekt.

## <a name="example"></a>Exempel

Du skapar ett serviceavtal för att tillhandahålla service för två hissar på en kunds anläggning.
Serviceavtalet har identifikations-ID SAL-001.

I formuläret är hissarna inställda som objekt EL-S/1000 och EL-L/1000 i formuläret för serviceobjekt.

Du kopplar serviceobjekten, EL-S/1000 och EL-L/1000, till serviceavtalet.

Du vill registrera ändringar i strukturlistan för serviceobjektet när du byter ut komponenter i objektet, så du kopplar en servicestrukturlista till serviceobjektrelationen enligt beskrivningen i följande tabell.

| Serviceobjekt | Relation – Serviceavtal | Servicestrukturlista   |
|----------------|------------------------------|---------------|
| EL-S/1000      | ID SAL-001                   | BOM-EL-S/1000 |
| EL-L/1000      | ID SAL-001                   | BOM-EL-L/1000 |

Eftersom det finns serviceobjektrelationer för avtalet kan du nu skapa serviceavtalsrader med dessa objekt, enligt beskrivningen som visas i följande tabell.

| transaktionstyp | Kategori           | Serviceobjekt |
|------------------|--------------------|----------------|
| Timme             | Inspektion         | EL-S/1000      |
| Timme             | Rengöring av växellåda  | EL-S/1000      |
| Artikel             | Rengöringsmaterial | EL-S/1000      |
| Timme             | Inspektion         | EL-L/1000      |
| Timme             | Rengöring av växellåda   | EL-L/1000      |
| Artikel             | Rengöringsmaterial | EL-L/1000      |

Vid ett servicebesök måste du byta ut växellådan på hissen EL-S/1000. Om du vill byta ut en komponent i objektet kan du öppna Strukturlistedesignern genom att använda den serviceobjektrelation du ställt in för det aktuella serviceavtalet.

Öppna Strukturlistedesignern genom att använda en serviceobjektrelation

1. Serviceavtal
2. Dubbelklicka på ett serviceavtal eller klicka på serviceavtal om du vill skapa ett nytt serviceavtal.
3. Klicka på fliken Inställningar.
4. Om du vill koppla en mallstrukturlista till ett serviceavtal klickar du på serviceobjekt.
5. I formuläret serviceobjekt klicka på Designer för att öppna formuläret Designer och ändra mallstrukturlistan.

## <a name="automatically-created-service-orders"></a>Automatiskt skapade serviceorder

Om en eller flera serviceorder skapas automatiskt för ett serviceavtal överförs även avtalets serviceobjektrelationer till de serviceorder som skapats.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]