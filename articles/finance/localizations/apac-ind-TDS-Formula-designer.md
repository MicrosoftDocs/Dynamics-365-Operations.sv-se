---
title: Formeldesigner för TDS-beräkningar
description: Det här avsnittet innehåller ett exempel på hur TDS (moms avdragen vid källa) beräknas baserat på formeln som definieras för varje TDS-momskod i den TDS-grupp som är kopplad till transaktionen.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 3d8e098243688ebf6977db97130592443e269973
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2022
ms.locfileid: "8408131"
---
# <a name="formula-designer-for-tds-calculations"></a>Formeldesigner för TDS-beräkningar

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller ett exempel på hur TDS (moms avdragen vid källa) beräknas baserat på formeln som definieras för varje TDS-momskod. TDS-momskoder definieras i TDS-gruppen som är kopplad till transaktionen. Innan du designar TDS-formler måste du göra de grundläggande inställningarna som krävs för TDS enligt stegen nedan. 

- Konfigurera TDS-komponentgrupper på sidan **Källskattekomponentgrupper**. 
- Ställ in TDS-komponenter och koppla TDS-komponentgruppen till TDS-komponenterna på sidan **Källskattekomponenter**. 
- Ställ in TDS-momskoder och koppla TDS-komponenter till momskoder på sidan **Källskattekoder**. 
- Konfigurera TDS-momsgrupper på sidan **Källskattegrupper**. Koppla sedan TDS-momskoderna till momsgruppen och definiera formeln på sidan **Formeldesigner**. 

**Exempelformel**

I det här exemplet kopplas TDS-gruppen Hyra till en inköpsfaktura som skapats för leverantör A. Fakturabeloppet är 1 000 000 kr. Läs följande tabell när du visar TDS-beräkningen för fakturan.

| TDS-grupp                                                   | TDS-momskoder som är kopplade till TDS-gruppen | Värde              | Momsunderlag (formeldesigner) | Beräkningsuttryck (formeldesigner) | Basbelopp | Beräknat TDS-belopp |
| ------------------------------------------------------------ | --------------------------------------- | ------------------ | --------------------------------- | :----------------------------------------: | ----------- | --------------------- |
| Hyra                                                         | TDS (TDS-komponent - TDS)                | 10 %                | Bruttobelopp                      |                                            | 100 000      | 10 000                 |
| Tilläggsavgift (TDS-komponent -Tilläggsavgift)                         | 10 %                                     | Exkl. bruttobelopp | +TDS                              |                   10000                    | 1 000        |                       |
| PE-inspektör (TDS-komponent- PE-inspektör)                            | 2 %                                      | Exkl. bruttobelopp | +TDS+Tilläggsavgift                    |                   11000                    | 220         |                       |
| SHE-inspektör (TDS-komponent - SHE-inspektör)                          | 1 %                                      | Exkl. bruttobelopp | +TDS+Tilläggsavgift                    |                   11000                    | 110         |                       |
| **Totalt** **TDS** **beräknat** **för** **den** **fakturan** | **11 330**                               |                    |                                   |                                            |             |                       |

Verifikationsposterna skapas på följande sätt.

| Konto           | Debet  | Kredit |
| ----------------- | ------ | ------ |
| Hyra              | 100 000 |        |
| Leverantör A          |        | 100 000 |
| Leverantör A          | 11 330  |        |
| Utgående TDS       |        | 10 000  |
| Utgående tilläggsavgift |        | 1 000   |
| Utgående PE-inspektör   |        | 220    |
| Utgående SHE-inspektör  |        | 110    |
