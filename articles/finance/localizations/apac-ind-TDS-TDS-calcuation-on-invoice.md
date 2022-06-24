---
title: TDS-beräkning på fakturor
description: Den här artikeln innehåller en referens för transaktioner där TDS (skatteavdrag vid källan) beräknas på fakturanivå.
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
ms.openlocfilehash: efc12e0839fe87e9db435f481ce1fd733c286d6c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855375"
---
# <a name="tds-calculation-on-invoices"></a>TDS-beräkning på fakturor

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller en referens för transaktioner där TDS (skatteavdrag vid källan) beräknas på fakturanivå.

| Serienummer | Transaktionstyp                                 | Transaktionsbelopp | Sökväg för sidnamn och val                                 | Kontotyp och motkontotyp                         |
| ------------- | ------------------------------------------------ | ------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 1.            | Inköp som gjorts från leverantör/registrera utgifter   | Debet eller kredit  | Sidan Allmänna journaler (Redovisning > Journalposter > Allmänna journaler), sidan Fakturagodkännandejournal (Leverantörsreskontra > Fakturor > Fakturagodkännande), sidan Fakturajournal (Leverantörsreskontra > Fakturor > Fakturajournal) | Redovisning (Dr.) Leverantör (Cr.).  Källskatt beräknas endast för kombinationen Leverantör-Redovisning när redovisningskontot har bokföringstypen **Inköp** **kontant**. |
| 2.            | Inköp som gjorts från kund/registrera utgifter | Debet eller kredit  | Sidan Allmänna journaler (Redovisning > Journalposter > Allmänna journaler), sidan Fakturajournal (Leverantörsreskontra > Fakturor > Fakturajournal) | Redovisning (Dr.) Kund (Cr.)                                 |
| 3.            | Inköp av anläggningstillgång från leverantör              | Debet eller kredit  | Sidan Allmänna journaler (Redovisning > Journalposter > Allmänna journaler), sidan Fakturaregisterjournal (Leverantörsreskontra > Fakturor > Fakturaregister), sidan Fakturajournal (Leverantörsreskontra > Fakturor > Fakturajournal) | Anläggningstillgångar (Dr.) Leverantör (Cr.)                             |
| 4.            | Inköp av anläggningstillgång från kund            | Debet eller kredit  | Sidan Allmänna journaler (Redovisning > Journalposter > Allmänna journaler), sidan Fakturajournal (Leverantörsreskontra > Fakturor > Fakturajournal) | Anläggningstillgångar (Dr.) Kund (Cr.)                           |
| 5.            | Inköpsfaktura (TDS-skuld)                  |                    | Sidan Inköpsorder (Leverantörsreskontra > Inköpsorder > Alla inköpsorder) |                                                              |
| 6.            | Försäljningsfaktura (TDS-kundreskontra)                  |                    | Sidan Försäljningsorder (Kundreskontra > Order > Alla försäljningsorder), Sidan Fritextfaktura (Kundreskontra > Fakturor > Alla fritextfakturor) |                                                              |
