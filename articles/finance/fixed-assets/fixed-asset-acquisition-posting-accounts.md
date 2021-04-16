---
title: Bokföringskonton för anskaffning av anläggningstillgångar
description: Det här avsnittet innehåller information om hur du ställer in redovisningsbokföringskonton för anskaffade tillgångar.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d4c1b4de2e58b964bcf6ab07929897083f4c826
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822019"
---
# <a name="fixed-asset-acquisition-posting-accounts"></a><span data-ttu-id="83d9e-103">Bokföringskonton för anskaffning av anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="83d9e-103">Fixed asset acquisition posting accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="83d9e-104">Det här avsnittet innehåller information om hur du ställer in redovisningsbokföringskonton för anskaffade tillgångar.</span><span class="sxs-lookup"><span data-stu-id="83d9e-104">This article explains how to set up general ledger posting accounts for acquiring assets.</span></span>

<span data-ttu-id="83d9e-105">Konton som används för bokföring av anskaffning kan variera beroende på metoden som används för anskaffning av tillgången.</span><span class="sxs-lookup"><span data-stu-id="83d9e-105">Accounts used for posting fixed asset acquisitions may vary depending upon the method used to acquire the asset.</span></span> <span data-ttu-id="83d9e-106">På sidan Bokföringsprofiler för anläggningstillgångar, på fliken Redovisningskonto, välj Anskaffnings och anskaffningsjustering för att ställa in Anläggningstillgångskontona som bokförs i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="83d9e-106">On the Fixed asset posting profiles page, on the Ledger accounts tab, select Acquisition and Acquisition adjustment to set up fixed asset accounts to post to the ledger.</span></span> 

<span data-ttu-id="83d9e-107">I journaler och inköpsorder debiteras den nya anläggningstillgångens anskaffningsvärde vanligtvis på balansräkningskontot.</span><span class="sxs-lookup"><span data-stu-id="83d9e-107">In journals and on purchase orders, Ledger account is typically the balance sheet account, where the acquisition value of the new fixed asset is debited.</span></span> <span data-ttu-id="83d9e-108">Det här kontot visas inte i journalen och kan inte ersättas i transaktioner.</span><span class="sxs-lookup"><span data-stu-id="83d9e-108">This account is not displayed in the journal and cannot be replaced in transactions.</span></span> 

<span data-ttu-id="83d9e-109">Motkonto är också ett balansräkningskonto.</span><span class="sxs-lookup"><span data-stu-id="83d9e-109">Offset account is also a balance sheet account.</span></span> <span data-ttu-id="83d9e-110">I den allmänna journalen och i Anläggningstillgångsjournalen är det här kontot ofta bankkontot som används för att betala anskaffningen av tillgången.</span><span class="sxs-lookup"><span data-stu-id="83d9e-110">In the general journal and in the fixed assets journal, this account often will be the bank account that is used to pay for the acquisition of the asset.</span></span> <span data-ttu-id="83d9e-111">Motkontot är ett standardkonto som föreslås i journalerna.</span><span class="sxs-lookup"><span data-stu-id="83d9e-111">The offset account is a default account, which is suggested in the journals.</span></span> <span data-ttu-id="83d9e-112">Det kan ändras i journalen till ett annat konto från kontoplanen eller till ett leverantörskonto, om anläggningstillgången har köpts från en leverantör.</span><span class="sxs-lookup"><span data-stu-id="83d9e-112">It can be changed in the journal to any other account from the chart of accounts or to a vendor account, if the fixed asset was purchase from a vendor.</span></span> 

<span data-ttu-id="83d9e-113">När Fakturajournal eller Inköpsorder i Leverantörsreskontra används för anskaffningar av anläggningstillgångar ersätts motkontot för Anläggningstillgångstransaktionen med ett leverantörskonto som valts för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="83d9e-113">When Invoice journal or Purchase orders in Accounts payable are used for fixed asset acquisitions, the offset account for the fixed asset transaction is replaced by the vendor account that is selected for the transaction.</span></span>

<span data-ttu-id="83d9e-114">För anskaffningar som bokförs med journalen Lager till anläggningstillgångar i Huvudbok köps inte anläggningstillgången från externa källor, utan överförs från företagets eget lager.</span><span class="sxs-lookup"><span data-stu-id="83d9e-114">For acquisitions posted using the Inventory to fixed assets journal in General ledger, the fixed asset is not bought from external sources, but transferred from the company's own inventory.</span></span> <span data-ttu-id="83d9e-115">Därför är motkontot ett lagerutleveranskonto för lagerartikeln i lagerhanteringen.</span><span class="sxs-lookup"><span data-stu-id="83d9e-115">Therefore, the offset account is an inventory issue account for the inventory item in Inventory management.</span></span>

<span data-ttu-id="83d9e-116">Mer information finns i [Förvärv av tillgångar genom upphandling](acquire-assets-procurement.md).</span><span class="sxs-lookup"><span data-stu-id="83d9e-116">For more information, see [Acquire assets through procurement](acquire-assets-procurement.md).</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]