---
title: Konfigurera tjänstledighets- och frånvaroparametrar
description: Definiera personalparametrar för tjänstledighet och frånvaro i Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2acb8502ebcab122a0a1ff21e9f5e23931026327
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010581"
---
# <a name="configure-leave-and-absence-parameters"></a><span data-ttu-id="dde71-103">Konfigurera tjänstledighets- och frånvaroparametrar</span><span class="sxs-lookup"><span data-stu-id="dde71-103">Configure leave and absence parameters</span></span>

<span data-ttu-id="dde71-104">Innan du ställer in tjänstledighets- och frånvaroplan i Dynamics 365 Human Resources kan det vara en bra idé att kontrollera inställningarna för alla relaterade personalparametrar, t.ex.:</span><span class="sxs-lookup"><span data-stu-id="dde71-104">Before you set up leave and absence plans in Dynamics 365 Human Resources, it's a good idea to verify the settings for all related human resources parameters, including:</span></span>

- <span data-ttu-id="dde71-105">Nummerserie för tjänstledighetsansökan</span><span class="sxs-lookup"><span data-stu-id="dde71-105">Number sequence for leave requests</span></span>
- <span data-ttu-id="dde71-106">Inställning av Family Medical and Leave Act (FMLA)</span><span class="sxs-lookup"><span data-stu-id="dde71-106">Family Medical and Leave Act (FMLA) settings</span></span>
- <span data-ttu-id="dde71-107">Inställningar för självbetjäning för medarbetare för tjänstledighets- och frånvaroansökningar</span><span class="sxs-lookup"><span data-stu-id="dde71-107">Employee self service settings for leave and absence requests</span></span>
- <span data-ttu-id="dde71-108">Parametrar för tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="dde71-108">Leave and absence parameters</span></span>

## <a name="view-and-change-human-resources-parameters"></a><span data-ttu-id="dde71-109">Visa och ändra personalparametrar</span><span class="sxs-lookup"><span data-stu-id="dde71-109">View and change human resources parameters</span></span>

1. <span data-ttu-id="dde71-110">På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="dde71-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="dde71-111">Under **Inställningar**, välj **Personalparametrar**.</span><span class="sxs-lookup"><span data-stu-id="dde71-111">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="dde71-112">På fliken **nummerserier** kontrollerar du **nummerseriekod** för **begäran om tjänstledighet-ID** och ändrar vid behov.</span><span class="sxs-lookup"><span data-stu-id="dde71-112">On the **Number sequences** tab, verify the **Number sequence code** for **Leave request ID** and change as necessary.</span></span> <span data-ttu-id="dde71-113">Den här inställningen avgör vilken sekvens som används för automatiskt tilldelning av ID:n för att lämna förfrågningar.</span><span class="sxs-lookup"><span data-stu-id="dde71-113">This setting determines the sequence used for automatically assigning IDs to leave requests.</span></span>

4. <span data-ttu-id="dde71-114">På fliken **FMLA** kontrollera FMLA-inställningar och ändra efter behov.</span><span class="sxs-lookup"><span data-stu-id="dde71-114">On the **FMLA** tab, verify the FMLA settings and change as necessary.</span></span>

5. <span data-ttu-id="dde71-115">På fliken **Självbetjäning för medarbetare** anger du om chefer kan ange tjänstledighets- och frånvaroansökningar för medarbetarnas räkning.</span><span class="sxs-lookup"><span data-stu-id="dde71-115">On the **Employee self service** tab, indicate whether managers can enter leave and absence requests on behalf of their employees.</span></span>

6. <span data-ttu-id="dde71-116">På fliken **tjänstledighet och frånvaro** kontrollera inställningar och ändra efter behov.</span><span class="sxs-lookup"><span data-stu-id="dde71-116">On the **Leave and absence** tab, verify the settings and change as necessary.</span></span>

7. <span data-ttu-id="dde71-117">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="dde71-117">Select **Save**.</span></span>

## <a name="configure-calendar-parameters"></a><span data-ttu-id="dde71-118">Konfigurera kalenderparametrar</span><span class="sxs-lookup"><span data-stu-id="dde71-118">Configure calendar parameters</span></span>

<span data-ttu-id="dde71-119">Om du har aktiverat funktionen förhandsgranskning av kalender för tjänstledighet och frånvaro måste du konfigurera ytterligare parametrar.</span><span class="sxs-lookup"><span data-stu-id="dde71-119">If you have enabled the Leave and absence calendar preview feature, you need to configure additional parameters.</span></span> 

[!include [banner](includes/preview-feature-leave-absence.md)]

> [!NOTE]
> <span data-ttu-id="dde71-120">För förhandsversionen från 3 februari 2020 är endast **väntande tjänstledighetsansökan** aktiverade.</span><span class="sxs-lookup"><span data-stu-id="dde71-120">For the preview release on February 3, 2020, only **Pending leave requests** are enabled.</span></span>

1. <span data-ttu-id="dde71-121">På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="dde71-121">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="dde71-122">Under **Inställningar**, välj **Personalparametrar**.</span><span class="sxs-lookup"><span data-stu-id="dde71-122">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="dde71-123">På fliken **Kalender** ändra kalenderinställningar och efter behov.</span><span class="sxs-lookup"><span data-stu-id="dde71-123">On the **Calendar** tab, change calendar settings as necessary.</span></span>

4. <span data-ttu-id="dde71-124">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="dde71-124">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="dde71-125">Se även</span><span class="sxs-lookup"><span data-stu-id="dde71-125">See also</span></span>

- [<span data-ttu-id="dde71-126">Översikt över tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="dde71-126">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
