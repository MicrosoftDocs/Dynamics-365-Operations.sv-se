---
title: Grundändring av ICMS-DIF-momsberäkningar för produkter från leverantörer i andra stater
description: Det här avsnittet beskriver konfigurationen för beräkningar av skattetypen ICMS-DIF när ett skattedokument tas emot i den brasilianska delstaten Rio Grande do Sul (RS) eller São Paulo (SP).
author: Kai-Cloud
ms.date: 1/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2022-1-17
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 63e3cbaaf77456b55f08ea91831ba9d49cb57185
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689168"
---
# <a name="basis-change-in-icms-dif-tax-calculations-for-products-from-suppliers-in-other-states"></a>Grundändring av ICMS-DIF-momsberäkningar för produkter från leverantörer i andra stater

Det här avsnittet beskriver konfigurationen för beräkningar av skattetypen **ICMS-DIF** när ett skattedokument tas emot i den brasilianska delstaten Rio Grande do Sul (RS) eller São Paulo (SP).

Enligt definitionen i delstatslagen måste Imposto sobre Circulação de Mercadorias e Serviços (ICMS) som samlas in följa denna regel:

*ICMS att samla in* = ([(*Operationsbelopp* – *ICMS från källa*) ÷ (1 – *ICMS % intern*)] × *ICMS % intern*) – *ICMS belopp från källan*

## <a name="example"></a>Exempel

Ett brasilianskt företag i delstaten RS får ett skattedokument för ett köp från en leverantör i delstaten SP. Företaget måste samla in skillnaden i procent av ICMS mellan RS-staten (18 procent) och SP-staten (12 procent). Underlaget måste dock beräknas enligt föregående regel.

- **Operationsbelopp:** 1 000,00 brasiliansk real (R$ 1 000,00)
- **ICMS mellanstatlig:** R$ 120,00
- **ICMS-procent i RS-status:** 18 procent
- **ICMS att samla in i RS-status:** (\[(1 000 – 120) ÷ (1 – 0,18)\] × 0.18 ) – 120 = R$ 73,17 

## <a name="resolution"></a>Lösning

Om du vill beräkna iCMS (ICMS-DIF) enligt reglerna för RS-staten måste du ställa in momskoder och en momsgrupp på följande sätt:

1. Skapa en momskod för att ta emot 12-procentig ICMS (för den andra status). Denna kod används för att registrera momsfordranbeloppet från leverantören.
2. Skapa en momskod för att samla in ICMS-DIF. Denna momskod ska ha ett procentbelopp på 18 procent (för egen delstat) för att definiera skillnaden mellan 18 och 12 procent. Ange momstypen till **ICMS-DIF**. Denna momskod måste definieras på följande sätt i beräkningsparametrarna:

    - I fältet **Ursprung** väljer du **Procent av bruttobelopp**.
    - I fältet **Marginalbas** väljer du **Nettobelopp per rad** eller **Nettobelopp av fakturasaldo**.
    - Definiera beskattningskoden så att den har ett räkenskapsvärde på **3**. På det här sättet skapas justeringstransaktionen automatiskt när modulen **Skatteböcker** aktiveras.
    - I konfigurationen för momsgruppen, välj **Använd moms** för **ICMS-DIF** momskoden.
