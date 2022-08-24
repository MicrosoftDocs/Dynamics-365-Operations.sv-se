---
title: Grundändring av ICMS-DIF-momsberäkningar för produkter från leverantörer i andra stater
description: Den här artikeln beskriver konfigurationen för beräkningar av skattetypen ICMS-DIF när ett skattedokument tas emot i den brasilianska delstaten Rio Grande do Sul (RS) eller São Paulo (SP).
author: Kai-Cloud
ms.date: 06/21/2022
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
ms.openlocfilehash: 1bd9982a3804778a27203b4311682ee8bc3c4841
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2022
ms.locfileid: "9218663"
---
# <a name="basis-change-dual-base-in-icms-dif-tax-calculations-for-products-from-suppliers-in-other-states"></a>Grundändring (dubbel bas) av ICMS-DIF-momsberäkningar för produkter från leverantörer i andra stater

Den här artikeln beskriver konfigurationen för beräkningar av skattetypen **ICMS-DIF** när ett skattedokument tas emot i den brasilianska delstaten Rio Grande do Sul (RS) eller São Paulo (SP).

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
    - I **Bidragsunderlag** välj **Nettobelopp per rad**.
    - Definiera beskattningskoden så att den har ett räkenskapsvärde på **3**. På det här sättet skapas justeringstransaktionen automatiskt när modulen **Skatteböcker** aktiveras.
    - I konfigurationen för momsgruppen, välj **Använd moms** för **ICMS-DIF** momskoden.

### <a name="use-the-delta-tax-rate-in-the-configuration-of-dual-base-icms-dif-sales-tax-codes"></a>Använd deltamomsen i när du konfigurerar dubbel bas för ICMS-DIF-momskoder

När de tidigare beskrivna inställningarna används beräknas **ICMS-DIF**-momskoden i basregeln. Den nominella momssatsen blir dock 18 procent, vilket skiljer sig från 6-procentskursen i den enkla basregeln. Denna skillnad orsakar inkonsekvenser i skattedokumentet och momsrapporteringen. Från och med Microsoft Dynamics 365 Finance version 10.0.29 kan du aktivera funktionen **(Brasilien) Konfigurera deltaskattesatsen i ICMS-DIF-skattekoden för det dubbla basfallet** i **Funktionshantering** för att ta bort inkonsekvensen.

- Förutom att utföra stegen i det föregående avsnittet väljer du **ICMS 12**-momskoden i fältet **Moms på moms**.
- Ange momssatsen för **ICMS-DIF**-momskoden till 18 procent. Fältet **Procent/Belopp** visar den nominella momssatsen som 6 procent.

> [!NOTE]
> Momskoderna **ICMS-DIF** och **ICMS 12** måste tilldelas i samma momsgrupp.

## <a name="basis-change-dual-base-in-icms-dif-tax-calculations-for-products-to-non-taxpayer-consumers-difal-in-other-states"></a>Grundändring (dubbel bas) av ICMS-DIF-momsberäkningar för produkter till icke-skattebetalare (DIFAL) i andra delstater

Aktivera funktionen **(Brasilien) Beräkning med dubbla baser för ICMS-DIFAL i försäljningstransaktioner** i **funktionshantering** för att stödja grundförändringen ICMS-DIF om handel till icke-skattebetalande konsumenter från en annan stat. Prov-ICMS-DIF-momskoden börjar gälla för försäljningsorder- och fritextfakturatransaktioner.

Aktivera funktionen **(Brasilien) Beräkning med dubbla baser för ICMS-DIFAL för IPI-ärenden** i **funktionshantering** för att stödja scenarier där handel med icke-skattebetalande konsumenter från en annan stat också är ansvarig för Imposto sobre Produtos Industrializados (IPI). Momsbeloppet för IPI-momskoden redovisas och används i ICMS-DIPHA-momsbasen.

- I sidhuvudet på försäljningsordern eller fritextfakturan, på snabbfliken **Räkenskapsuppgifter** måste alternativet **Slutlig användare** vara inställt på **Ja**.
- I sidhuvudet på inköpsordern eller leverantörsfakturan, på snabbfliken **Räkenskapsuppgifter** måste alternativet **Användning och förbrukning** vara inställt på **Ja**.
