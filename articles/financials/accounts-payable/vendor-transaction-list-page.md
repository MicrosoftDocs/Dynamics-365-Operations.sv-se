---
title: "Leverantörstransaktionssida"
description: "Det här avsnittet innehåller information om leverantörstransaktionssidan för Microsoft Dynamics 365 for Finance and Operations."
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: 1ef7d97f059801f2fb2c0d451546b57055208f81
ms.contentlocale: sv-se
ms.lasthandoff: 08/31/2018

---

# <a name="vendor-transaction-list-page"></a><span data-ttu-id="5d8e3-103">Leverantörstransaktionssida</span><span class="sxs-lookup"><span data-stu-id="5d8e3-103">Vendor transaction list page</span></span>

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a><span data-ttu-id="5d8e3-104">Visa kvittningar</span><span class="sxs-lookup"><span data-stu-id="5d8e3-104">View settlements</span></span>

<span data-ttu-id="5d8e3-105">Fliken **Visa kvittningar** i åtgärdsfönstret ger snabb tillgång till kvittningshistoriken och mer information om hela kvittningstransaktionen.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-105">The **View settlements** tab on the action pane provides quick access to settlement history and more information about the whole settlement transaction.</span></span> <span data-ttu-id="5d8e3-106">Du kan också visa ytterligare transaktioner som är relaterade till den valda transaktionen, antingen eftersom de tillhörde samma kvittning eller eftersom de är betalningar som skapades i samma betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-106">You can also show additional transactions that are related to the selected transaction, either because they were part of the same settlement or because they are payments that were created in the same payment journal.</span></span>

1. <span data-ttu-id="5d8e3-107">Välj **Leverantörsreskontra \>Alla leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-107">Select **Accounts payable \> All vendors**.</span></span>
2. <span data-ttu-id="5d8e3-108">Markera en leverantör som har transaktioner och välj **Leverantör \>Transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-108">Select a vendor that has transactions, and then select **Vendor \> Transactions**.</span></span>
3. <span data-ttu-id="5d8e3-109">Välj en transaktion som du vill undersöka.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-109">Select a transaction to research.</span></span>
4. <span data-ttu-id="5d8e3-110">Välj fliken **Visa kvittningar** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-110">Select the **View settlements** tab on the action pane.</span></span>

    <span data-ttu-id="5d8e3-111">Dialogrutan **Visa kvittningar** öppnas och visar den valda transaktionen och alla dokument som kvittas mot den.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-111">The **View settlements** dialog box opens and shows the selected transaction and all documents that are settled against it.</span></span> <span data-ttu-id="5d8e3-112">Denna dialogruta liknar kvittningshistorikvyn, men den innehåller alla relaterade dokument.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-112">This dialog box resembles the settlement history view, but it includes all related documents.</span></span>

5. <span data-ttu-id="5d8e3-113">Du kan utföra olika uppgifter från den här dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-113">You can perform various tasks from this dialog box.</span></span> <span data-ttu-id="5d8e3-114">Markera en eller flera verifikationer och välj en av följande menyer:</span><span class="sxs-lookup"><span data-stu-id="5d8e3-114">Select one or more vouchers, and then select one of the following menus:</span></span>

   - <span data-ttu-id="5d8e3-115">**Visa redovisning** – Alla verifikationer som är relaterade till de valda dokumenten visas.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-115">**View accounting** – All vouchers that are related to the selected documents appear.</span></span> <span data-ttu-id="5d8e3-116">Välj **Stäng** för att stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-116">Select **Close** to close the dialog box.</span></span>
   - <span data-ttu-id="5d8e3-117">**Exportera** – Exportera de valda verifikationerna till Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-117">**Export** – Export the selected vouchers to Microsoft Excel.</span></span>
   - <span data-ttu-id="5d8e3-118">**Visa relaterade betalningar** – Alla transaktioner i betalningsjournal som skapades i betalningsjournalen som är relaterade till det valda dokumentet visas.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-118">**View related payments** – All the payment journal transactions that were created in the payment journal that is related to the selected document appear.</span></span> <span data-ttu-id="5d8e3-119">Dessutom visas alla kvittningar som är relaterade till betalningarna.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-119">In addition, all the settlements that are related to those payments appear.</span></span> <span data-ttu-id="5d8e3-120">Etiketten över denna many ändras till **Visa kvittningar**.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-120">The label of this menu also changes to **View settlements**.</span></span> <span data-ttu-id="5d8e3-121">Välj **Visa kvittningar** om du endast vill visa transaktioner som visades när du öppnade dialogrutan **Visa kvittningar**.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-121">Select **View settlements** to show only the transactions that were shown when you first opened the  **View settlements** dialog box.</span></span>
    - <span data-ttu-id="5d8e3-122">**Kvitta transaktioner** – Denna meny visas om det ursprungliga dokumentet som valdes inte kvittats helt.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-122">**Settle transactions** – This menu appears if the original document that was selected wasn't fully settled.</span></span> <span data-ttu-id="5d8e3-123">När du väljer den visas dialogrutan **kvitta transaktioner** där du kan välja transaktioner för kvittning.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-123">When you select it, the **Settle transactions** dialog box appears, where you can select transactions for settlement.</span></span>
    - <span data-ttu-id="5d8e3-124">**Ångra kvittningar** – Denna meny visas om det ursprungliga dokumentet som valdes inte kvittats helt.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-124">**Undo settlements** – This menu appears if the original document that was selected was fully settled.</span></span> <span data-ttu-id="5d8e3-125">När du väljer den visas dialogrutan **Ångra kvittningar** där du kan ångra kvittningar som har gjorts för det dokumentet.</span><span class="sxs-lookup"><span data-stu-id="5d8e3-125">When you select it, the **Undo settlements** dialog box appears, where you can undo the settlements that were done for that document.</span></span>

