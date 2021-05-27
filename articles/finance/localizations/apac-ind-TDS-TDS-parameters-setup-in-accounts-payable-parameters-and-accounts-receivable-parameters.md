---
title: Konfigurera TDS-parametrar i Leverantörsreskontra och Kundreskontra
description: I det här avsnittet beskrivs hur du ställer in parametrar i leverantörsreskontra och kundreskontra för att stödja skatteavdrag vid källa (TDS).
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
ms.openlocfilehash: 4540cdfff2362d8fb7cc2b4cccf9c340be9750ce
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023598"
---
# <a name="set-tds-parameters-in-accounts-payable-and-accounts-receivable"></a><span data-ttu-id="c3d28-103">Konfigurera TDS-parametrar i Leverantörsreskontra och Kundreskontra</span><span class="sxs-lookup"><span data-stu-id="c3d28-103">Set TDS parameters in Accounts payable and Accounts receivable</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c3d28-104">I det här avsnittet beskrivs hur du ställer in parametrar i leverantörsreskontra och kundreskontra för att stödja skatteavdrag vid källa (TDS).</span><span class="sxs-lookup"><span data-stu-id="c3d28-104">This topic explains how to set parameters in Accounts payable and Accounts receivable to support Tax Deducted at Source (TDS) deductions.</span></span>

1. <span data-ttu-id="c3d28-105">Gå till **Skatt \> Konfiguration \> Parametrar \> Parametrar för kundreskontra**.</span><span class="sxs-lookup"><span data-stu-id="c3d28-105">Go to **Tax \> Setup \> Parameters \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="c3d28-106">Under fliken **Uppdateringar** väljer du **Uppdatera orderrader** för att öppna dialogrutan **Uppdatera orderrader**.</span><span class="sxs-lookup"><span data-stu-id="c3d28-106">On the **Updates** tab, select **Update order lines** to open the **Update order lines** dialog box.</span></span>
3. <span data-ttu-id="c3d28-107">I avsnittet **TDS-grupp**, i fältet **Uppdatera TDS-grupp**, anger du metoden som ska användas för att uppdatera TDS-gruppen på radnivå.</span><span class="sxs-lookup"><span data-stu-id="c3d28-107">In the **TDS group** section, in the **Updating TDS group** field, specify the method to use to update the TDS group at the line level.</span></span> <span data-ttu-id="c3d28-108">Den här inställningen används när TDS-gruppen uppdateras i en orderrubrik.</span><span class="sxs-lookup"><span data-stu-id="c3d28-108">This setting is used when the TDS group is updated on an order header.</span></span> <span data-ttu-id="c3d28-109">Följande alternativ är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="c3d28-109">The following options are available:</span></span>

    - <span data-ttu-id="c3d28-110">**Aldrig** – TDS-gruppen är inte uppdaterad på orderraderna när den uppdateras i orderrubriken.</span><span class="sxs-lookup"><span data-stu-id="c3d28-110">**Never** – The TDS group isn't updated on the order lines when it's updated on the order header.</span></span>
    - <span data-ttu-id="c3d28-111">**Alltid** – TDS-gruppen uppdateras automatiskt på orderraderna när den uppdateras i orderrubriken.</span><span class="sxs-lookup"><span data-stu-id="c3d28-111">**Always** – The TDS group is automatically updated on the order lines when it's updated on the order header.</span></span>
    - <span data-ttu-id="c3d28-112">**Uppmaning** – Användarna får ett meddelande som uppmanar dem att uppdatera TDS-gruppen på orderraderna.</span><span class="sxs-lookup"><span data-stu-id="c3d28-112">**Prompt** – Users receive a message that prompts them to update the TDS group on the order lines.</span></span>
4. <span data-ttu-id="c3d28-113">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3d28-113">Select **OK**.</span></span>

    <span data-ttu-id="c3d28-114">[![Dialogrutan Uppdatera orderrader](./media/apac-ind-TDS-26.PNG)](./media/apac-ind-TDS-26.PNG)</span><span class="sxs-lookup"><span data-stu-id="c3d28-114">[![Update order lines dialog box](./media/apac-ind-TDS-26.PNG)](./media/apac-ind-TDS-26.PNG)</span></span>

5. <span data-ttu-id="c3d28-115">Gå till **Skatt \> Konfiguration \> Parametrar \> Parametrar för leverantörsreskontra**.</span><span class="sxs-lookup"><span data-stu-id="c3d28-115">Go to **Tax \> Setup \> Parameters \> Accounts payable parameters**.</span></span>
6. <span data-ttu-id="c3d28-116">Under fliken **Allmänt**, under snabbfliken **Dela upp baserat på leveransinformation**, ställer du in alternativet **Produktinleverans** på **Ja** för att bokföra och dela upp en produktinleverans som har olika leveransadresser och skattekontonummer (TAN).</span><span class="sxs-lookup"><span data-stu-id="c3d28-116">On the **General** tab, on the **Split based on delivery information** FastTab, set the **Product receipt** option to **Yes** to post and split a product receipt that has different delivery addresses and tax account numbers (TANs).</span></span> <span data-ttu-id="c3d28-117">Om det här alternativet är inställt på **Nej**, kan du inte bokföra en inköpsföljesedel som har olika leveransadresser och TAN.</span><span class="sxs-lookup"><span data-stu-id="c3d28-117">If this option is set to **No**, you can't post a purchase packing slip that has different delivery addresses and TANs.</span></span>
7. <span data-ttu-id="c3d28-118">Ställ in alternativet **Faktura** på **Ja** för att bokföra och dela upp en inköpsfaktura som har olika leveransadresser och TAN.</span><span class="sxs-lookup"><span data-stu-id="c3d28-118">Set the **Invoice** option to **Yes** to post and split a purchase invoice that has different delivery addresses and TANs.</span></span>

    <span data-ttu-id="c3d28-119">[![Snabbfliken Dela upp baserat på leveransinformation](./media/apac-ind-TDS-25.png)](./media/apac-ind-TDS-25.png)</span><span class="sxs-lookup"><span data-stu-id="c3d28-119">[![Split based on delivery information FastTab](./media/apac-ind-TDS-25.png)](./media/apac-ind-TDS-25.png)</span></span>

8. <span data-ttu-id="c3d28-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c3d28-120">Close the page.</span></span>
