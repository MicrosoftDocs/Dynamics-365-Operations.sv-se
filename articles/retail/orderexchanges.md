---
title: Konfigurera och behandla ett utbyte för en returorder
description: I detta avsnitt beskriver vi hur du konfigurerar ett utbyte för en returorder i Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 11/12/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 45b628376a483d3d639e5c018dd93570ed8ce7af
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "302891"
---
# <a name="configure-and-process-an-exchange-on-a-return-order"></a><span data-ttu-id="33bf2-103">Konfigurera och behandla ett utbyte för en returorder</span><span class="sxs-lookup"><span data-stu-id="33bf2-103">Configure and process an exchange on a return order</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="33bf2-104">I tidigare versioner av Microsoft Dynamics 365 for Retail behandlades returer mot en kundorder genom att returorderdokumentet i Retail Headquarters användes.</span><span class="sxs-lookup"><span data-stu-id="33bf2-104">In previous versions of Microsoft Dynamics 365 for Retail, returns against customer orders were processed by using the return order document in Retail headquarters.</span></span> <span data-ttu-id="33bf2-105">Returorderdokumentet går dock att använda för att enbart behandla produkter som returneras.</span><span class="sxs-lookup"><span data-stu-id="33bf2-105">However, the return order document can be used to process only products that are being returned.</span></span> <span data-ttu-id="33bf2-106">De returnerade produkterna anges med en negativ kvantitet på returorderraderna.</span><span class="sxs-lookup"><span data-stu-id="33bf2-106">The returned products are indicated by a negative quantity on the return order lines.</span></span> <span data-ttu-id="33bf2-107">Försäljningar anges med en positiv kvantitet.</span><span class="sxs-lookup"><span data-stu-id="33bf2-107">By contrast, sales are indicated by a positive quantity.</span></span> <span data-ttu-id="33bf2-108">Returorderdokumentet stöder emellertid inte positiva kvantiteter.</span><span class="sxs-lookup"><span data-stu-id="33bf2-108">However, the return order document doesn't support positive quantities.</span></span> <span data-ttu-id="33bf2-109">Tidigare versioner av Retail stödde på grund av denna begränsning inte scenarier där produktbyten gjordes med hjälp av returorderdokumentet.</span><span class="sxs-lookup"><span data-stu-id="33bf2-109">Because of this limitation, previous versions of Retail didn't support scenarios where product exchanges are done by using the return order document.</span></span>

<span data-ttu-id="33bf2-110">Denna funktion har dock lagts till så att det ska gå att byta ut produkter på returorder.</span><span class="sxs-lookup"><span data-stu-id="33bf2-110">However, functionality has been added to support scenarios where exchanges are done on return orders.</span></span> <span data-ttu-id="33bf2-111">Retail använder nu försäljningsorderdokumentet i stället för returorderdokumentet för att bearbeta dessa typer av transaktioner.</span><span class="sxs-lookup"><span data-stu-id="33bf2-111">Retail now uses the sales order document instead of the return order document to process these types of transactions.</span></span>

## <a name="configure-retail-to-support-exchanges-on-return-orders"></a><span data-ttu-id="33bf2-112">Konfigurera Retail för att stödja utbyten med returorder</span><span class="sxs-lookup"><span data-stu-id="33bf2-112">Configure Retail to support exchanges on return orders</span></span>

<span data-ttu-id="33bf2-113">Gör så här för att konfigurera systemet så att de stöder utbyten med returorder.</span><span class="sxs-lookup"><span data-stu-id="33bf2-113">Follow these steps to configure the system to support exchanges on return orders.</span></span>

1. <span data-ttu-id="33bf2-114">Öppna **Retail \> Administrationsinställning \> Parametrar \> Retail-parametrar**.</span><span class="sxs-lookup"><span data-stu-id="33bf2-114">Go to **Retail \> Headquarters setup \> Parameters \> Retail parameters**.</span></span> <span data-ttu-id="33bf2-115">Ge alternativet **Behandla returorder som försäljningsorder** på snabbfliken **Kundorder** värdet **Ja**.</span><span class="sxs-lookup"><span data-stu-id="33bf2-115">On the **Customer orders** FastTab, set the **Process return orders as sales orders** option to **Yes**.</span></span>
2. <span data-ttu-id="33bf2-116">Kör jobbet **Globalt konfigurationsfördelningsschema** (**1110**).</span><span class="sxs-lookup"><span data-stu-id="33bf2-116">Run the **Global configuration distribution schedule** job (**1110**).</span></span>

## <a name="make-an-exchange"></a><span data-ttu-id="33bf2-117">Gör ett byte</span><span class="sxs-lookup"><span data-stu-id="33bf2-117">Make an exchange</span></span>

<span data-ttu-id="33bf2-118">När systemet är konfigurerat enligt beskrivningen i föregående avsnitt kommer kassaanvändaren fortfarande välja en försäljningsorder eller en försäljningsfaktura för att behandla en retur, precis som i tidigare versioner av Retail.</span><span class="sxs-lookup"><span data-stu-id="33bf2-118">After the system is configured as described in the previous section, the point of sale (POS) user will still select a sales order or sales invoice to process a return, as in previous versions of Retail.</span></span> <span data-ttu-id="33bf2-119">Men när de returnerade artiklarna läggs till i kundvagnen kommer användaren att kunna lägga till nya försäljningsrader i vagnen.</span><span class="sxs-lookup"><span data-stu-id="33bf2-119">However, after the return items are added to the cart, the user will be able to add new sales lines to the cart.</span></span>

<span data-ttu-id="33bf2-120">För dessa nya försäljningsrader måste användaren ange alla attribut som krävs för att behandla en kundorderrad.</span><span class="sxs-lookup"><span data-stu-id="33bf2-120">For these new sales lines, the user must define all the attributes that are required in order to process a customer order line.</span></span> <span data-ttu-id="33bf2-121">Bland dessa attribut ingår uppfyllelseplatsen och leveransmetoden.</span><span class="sxs-lookup"><span data-stu-id="33bf2-121">These attributes include the delivery method and fulfillment location.</span></span> <span data-ttu-id="33bf2-122">Betalningen för transaktionen är nettot av returorderraderna och försäljningsorderraderna.</span><span class="sxs-lookup"><span data-stu-id="33bf2-122">The payment that is due for the transaction will be a net of the return order lines and sales order lines.</span></span> <span data-ttu-id="33bf2-123">När transaktionen betalas bokförs returordern som ett försäljningsorderdokument i Retail Headquarters, och systemet fakturerar omedelbart returraderna.</span><span class="sxs-lookup"><span data-stu-id="33bf2-123">When payment is tendered for the transaction, the return order will be posted as a sales order document in Retail headquarters, and the system will immediately invoice the return lines.</span></span>

<span data-ttu-id="33bf2-124">Tre nya beloppsfält har lagts till i kundvagnen för att ge bättre inblick i vagnens olika belopp.</span><span class="sxs-lookup"><span data-stu-id="33bf2-124">To provide better visibility into the various amounts for the cart, three new amount fields have been added to the cart.</span></span> <span data-ttu-id="33bf2-125">Du kan använda skärmdesignern för att göra dessa nya fält tillgängliga i kassaanvändargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="33bf2-125">You can use the screen designer to make these new fields available in the POS user interface (UI).</span></span>

- <span data-ttu-id="33bf2-126">**Utnyttjad insättning** – Insättningsbeloppet som används i en transaktion när användaren hämtar upp en kundorder.</span><span class="sxs-lookup"><span data-stu-id="33bf2-126">**Deposit applied** – The deposit amount that is applied on a transaction when the user does a customer order pickup.</span></span> <span data-ttu-id="33bf2-127">Om det inte finns någon insättningsåsidosättning och en tioprocentig insättning har konfigurerats är beloppet i detta fält 90 procent av kundorderns totalbelopp.</span><span class="sxs-lookup"><span data-stu-id="33bf2-127">If there is no deposit override, and a 10-percent deposit is configured, the amount in this field is 90 percent of the total amount of the customer order.</span></span>
- <span data-ttu-id="33bf2-128">**Utför belopp** – Det totala beloppet för rader där leveransläget var **Utför** när kundordern skapades eller redigerades, eller under ett kundorderutbyte.</span><span class="sxs-lookup"><span data-stu-id="33bf2-128">**Carry out amount** – The total amount for lines where the delivery mode was set to **Carry out** when the customer order was created or edited, or during a customer order exchange.</span></span> <span data-ttu-id="33bf2-129">Beloppet i detta fält omfattar moms och avgifter.</span><span class="sxs-lookup"><span data-stu-id="33bf2-129">The amount in this field includes taxes and charges.</span></span>
- <span data-ttu-id="33bf2-130">**Returbelopp** – Det totala beloppet för rader med negativa kvantiteter under kundorderutbytet.</span><span class="sxs-lookup"><span data-stu-id="33bf2-130">**Return amount** – The total amount for lines that have negative quantities during the customer order exchange.</span></span> <span data-ttu-id="33bf2-131">Beloppet i detta fält omfattar moms och avgifter.</span><span class="sxs-lookup"><span data-stu-id="33bf2-131">The amount in this field includes taxes and charges.</span></span>
