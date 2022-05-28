---
title: TDS-beräkning på koncerninterna transaktioner
description: Det här ämnet beskriver den process som används för att beräkna skatteavdrag källan (TDS) på koncerninterna transaktioner i faser.
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
ms.openlocfilehash: 381b00c64e3e3a09a245c82cbe1f1599986a49aa
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726989"
---
# <a name="tds-calculation-on-intercompany-transactions"></a>TDS-beräkning på koncerninterna transaktioner

[!include [banner](../includes/banner.md)]

Det här ämnet beskriver den process som används för att beräkna skatteavdrag källan (TDS) på koncerninterna transaktioner i faser.

När en koncernintern inköpsorder eller försäljningsorder skapas används standardgruppen för TDS som definieras för kunden eller leverantören för att beräkna TDS-beloppet. TDS-beloppet bokförs på leverantörskontona för återställd eller leverantörsreskontra efter att fakturan har bokförts.

En koncernintern försäljnings- eller inköpsorder skapas automatiskt för den ursprungliga inköpsordern eller försäljningsordern. Standardgruppen för TDS visas på den koncerninterna ordern, så att TDS kan beräknas. Du kan ändra TDS-gruppen. Fakturan kan endast bokföras om nettofakturabeloppet på den koncerninterna order som skapas automatiskt matchar nettofakturabeloppet på den ursprungliga ordern. (Nettobeloppet är fakturabeloppet efter avdrag för TDS.)

Till exempel skapas en försäljningsfaktura för 50 000 och **10 %** TDS-gruppen är kopplad till den. Det bokförda fakturabeloppet är 45 000 och det bokförda TDS-beloppet för försäljningsfakturan är 5 000. En inköpsorder skapas automatiskt för den koncerninterna försäljningsordern och **10 %** TDS-gruppen är kopplad till den. Om du ändrar TDS-gruppen till **15 %**, kan du inte bokföra fakturan, eftersom nettofakturabeloppet på den koncerninterna försäljningsordern som skapades automatiskt inte stämmer överens med nettofakturabeloppet på den ursprungliga försäljningsordern.

En betalningsjournal som skapas för en koncernintern faktura bokförs automatiskt. Den betalningsjournalen kan endast bokföras om nettobetalningsbeloppet på den matchar nettobetalningsbeloppet i den ursprungliga betalningsjournalen.
