---
title: TDS-beräkning på koncerninterna transaktioner
description: Det här ämnet beskriver den process som används för att beräkna skatteavdrag källan (TDS) på koncerninterna transaktioner i faser.
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
ms.openlocfilehash: 0e304747cc93bfe0a39beababc3182ca14664b11
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023601"
---
# <a name="tds-calculation-on-intercompany-transactions"></a><span data-ttu-id="582ca-103">TDS-beräkning på koncerninterna transaktioner</span><span class="sxs-lookup"><span data-stu-id="582ca-103">TDS calculation on intercompany transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="582ca-104">Det här ämnet beskriver den process som används för att beräkna skatteavdrag källan (TDS) på koncerninterna transaktioner i faser.</span><span class="sxs-lookup"><span data-stu-id="582ca-104">This topic describes the process that is used to calculate Tax Deducted at Source (TDS) on intercompany transactions in phases.</span></span>

<span data-ttu-id="582ca-105">När en koncernintern inköpsorder eller försäljningsorder skapas används standardgruppen för TDS som definieras för kunden eller leverantören för att beräkna TDS-beloppet.</span><span class="sxs-lookup"><span data-stu-id="582ca-105">When an intercompany purchase order or sales order is created, the default TDS group that is defined for the customer or vendor is used to calculate the TDS amount.</span></span> <span data-ttu-id="582ca-106">TDS-beloppet bokförs på leverantörskontona för återställd eller leverantörsreskontra efter att fakturan har bokförts.</span><span class="sxs-lookup"><span data-stu-id="582ca-106">The TDS amount is posted to the recoverable or payable accounts after the invoice is posted.</span></span>

<span data-ttu-id="582ca-107">En koncernintern försäljnings- eller inköpsorder skapas automatiskt för den ursprungliga inköpsordern eller försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="582ca-107">An intercompany sales order or purchase order is automatically created for the original purchase order or sales order.</span></span> <span data-ttu-id="582ca-108">Standardgruppen för TDS visas på den koncerninterna ordern, så att TDS kan beräknas.</span><span class="sxs-lookup"><span data-stu-id="582ca-108">The default TDS group is shown on the intercompany order, so that TDS can be calculated.</span></span> <span data-ttu-id="582ca-109">Du kan ändra TDS-gruppen.</span><span class="sxs-lookup"><span data-stu-id="582ca-109">You can change the TDS group.</span></span> <span data-ttu-id="582ca-110">Fakturan kan endast bokföras om nettofakturabeloppet på den koncerninterna order som skapas automatiskt matchar nettofakturabeloppet på den ursprungliga ordern.</span><span class="sxs-lookup"><span data-stu-id="582ca-110">The invoice can be posted only if the net invoice amount on the intercompany order that is automatically created matches the net invoice amount on the original order.</span></span> <span data-ttu-id="582ca-111">(Nettobeloppet är fakturabeloppet efter avdrag för TDS.)</span><span class="sxs-lookup"><span data-stu-id="582ca-111">(The net amount is the invoice amount after TDS is deducted.)</span></span>

<span data-ttu-id="582ca-112">Till exempel skapas en försäljningsfaktura för 50 000 och **10 %** TDS-gruppen är kopplad till den.</span><span class="sxs-lookup"><span data-stu-id="582ca-112">For example, a sales invoice is created for 50,000, and the **10%** TDS group is attached to it.</span></span> <span data-ttu-id="582ca-113">Det bokförda fakturabeloppet är 45 000 och det bokförda TDS-beloppet för försäljningsfakturan är 5 000.</span><span class="sxs-lookup"><span data-stu-id="582ca-113">The posted invoice amount is 45,000, and the posted TDS amount for the sales invoice is 5,000.</span></span> <span data-ttu-id="582ca-114">En inköpsorder skapas automatiskt för den koncerninterna försäljningsordern och **10 %** TDS-gruppen är kopplad till den.</span><span class="sxs-lookup"><span data-stu-id="582ca-114">A purchase order is automatically created for the intercompany sales order, and the  **10%** TDS group is attached to it.</span></span> <span data-ttu-id="582ca-115">Om du ändrar TDS-gruppen till **15 %**, kan du inte bokföra fakturan, eftersom nettofakturabeloppet på den koncerninterna försäljningsordern som skapades automatiskt inte stämmer överens med nettofakturabeloppet på den ursprungliga försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="582ca-115">If you change the TDS group to **15%**, you can't post the invoice, because the net invoice amount of the intercompany sales order that was automatically created doesn't match the net invoice amount of the original sales order.</span></span>

<span data-ttu-id="582ca-116">En betalningsjournal som skapas för en koncernintern faktura bokförs automatiskt.</span><span class="sxs-lookup"><span data-stu-id="582ca-116">A payment journal that is created for an intercompany invoice is automatically posted.</span></span> <span data-ttu-id="582ca-117">Den betalningsjournalen kan endast bokföras om nettobetalningsbeloppet på den matchar nettobetalningsbeloppet i den ursprungliga betalningsjournalen.</span><span class="sxs-lookup"><span data-stu-id="582ca-117">That payment journal can be posted only if the net payment amount on it matches the net payment amount on the original payment journal.</span></span>
