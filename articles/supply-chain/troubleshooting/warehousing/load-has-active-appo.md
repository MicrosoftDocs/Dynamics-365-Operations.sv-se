---
title: Du kan inte bekräfta en leverans på grund av ett problem med kalendern.
description: Du kan inte bekräfta en leverans på grund av ett problem med kalendern.
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f1fccd10d8867252f32b37c77f9a3bad54157bdd
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938555"
---
# <a name="you-cant-confirm-a-shipment-because-of-an-issue-with-the-calendar"></a><span data-ttu-id="f786d-103">Du kan inte bekräfta en leverans på grund av ett problem med kalendern.</span><span class="sxs-lookup"><span data-stu-id="f786d-103">You can't confirm a shipment because of an issue with the calendar</span></span>

<span data-ttu-id="f786d-104">Felkod: TRX2716</span><span class="sxs-lookup"><span data-stu-id="f786d-104">Error code: TRX2716</span></span>

## <a name="symptoms"></a><span data-ttu-id="f786d-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="f786d-105">Symptoms</span></span>

<span data-ttu-id="f786d-106">När du försöker bekräfta en leverans visas följande felmeddelande i systemet:</span><span class="sxs-lookup"><span data-stu-id="f786d-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="f786d-107">Kalendertypen %1 kräver att mötet %2 checkas in och ut.</span><span class="sxs-lookup"><span data-stu-id="f786d-107">The calendar type %1 requires the appointment %2 to be checked in and out.</span></span>

<span data-ttu-id="f786d-108">Du kan därför inte bekräfta leveransen för beläggningen.</span><span class="sxs-lookup"><span data-stu-id="f786d-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="f786d-109">Orsak</span><span class="sxs-lookup"><span data-stu-id="f786d-109">Cause</span></span>

<span data-ttu-id="f786d-110">Aktiva möten för beläggningen finns.</span><span class="sxs-lookup"><span data-stu-id="f786d-110">Active appointments for the load exist.</span></span> <span data-ttu-id="f786d-111">Det finns till exempel en regel som säger att förarna måste checka in.</span><span class="sxs-lookup"><span data-stu-id="f786d-111">For example, there is a rule that requires driver check-in.</span></span> <span data-ttu-id="f786d-112">Därför befinner sig beläggningen i ett skick där leveransbekräftelsen misslyckas.</span><span class="sxs-lookup"><span data-stu-id="f786d-112">Therefore, the load is currently in a state where shipment confirmation fails.</span></span>

## <a name="resolution"></a><span data-ttu-id="f786d-113">Upplösning</span><span class="sxs-lookup"><span data-stu-id="f786d-113">Resolution</span></span>

<span data-ttu-id="f786d-114">Du måste undersöka och åtgärda eventuella problem med de aktiva möten som är kopplade till beläggningen.</span><span class="sxs-lookup"><span data-stu-id="f786d-114">You must investigate and fix any issues with the active appointments that are linked to the load.</span></span>

1. <span data-ttu-id="f786d-115">Gå till **Lagerstyrning \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="f786d-115">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="f786d-116">Välj den beläggning som leveransen inte kan bekräftas för.</span><span class="sxs-lookup"><span data-stu-id="f786d-116">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="f786d-117">I åtgärdsfönstret, på fliken **Transport**, i gruppen **Möten**, väljer du **Transportplanering**.</span><span class="sxs-lookup"><span data-stu-id="f786d-117">On the Action Pane, on the **Transportation** tab, in the **Appointments** group, select **Appointment scheduling**.</span></span>
1. <span data-ttu-id="f786d-118">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="f786d-118">Follow one of these steps:</span></span>

    - <span data-ttu-id="f786d-119">Kontrollera att förarens in-/utcheckning slutförs för det här mötet.</span><span class="sxs-lookup"><span data-stu-id="f786d-119">Make sure that driver check-in/check-out is completed for the appointment.</span></span>
    - <span data-ttu-id="f786d-120">Fyll i eller annullera mötet.</span><span class="sxs-lookup"><span data-stu-id="f786d-120">Complete or cancel the appointment.</span></span>
    - <span data-ttu-id="f786d-121">Inaktivera alternativet **Förarincheckning krävs** för den relaterade mötesregeln.</span><span class="sxs-lookup"><span data-stu-id="f786d-121">Disable the **Driver check-in required** option for the related appointment rule.</span></span>
