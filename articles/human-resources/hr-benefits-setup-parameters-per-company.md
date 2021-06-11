---
title: Konfigurera parametrar för förmånshantering per företag
description: Konfigurera parametrar för förmånshantering per företag i Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d2c564f0dfd1cbe44566269c97218450fedf2173
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6057632"
---
# <a name="configure-benefits-management-parameters-per-company"></a><span data-ttu-id="4a822-103">Konfigurera parametrar för förmånshantering per företag</span><span class="sxs-lookup"><span data-stu-id="4a822-103">Configure Benefits management parameters per company</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="4a822-104">För varje organisation som erbjuder förmåner måste du konfigurera inställningar för förmånsbekräftelsemeddelanden.</span><span class="sxs-lookup"><span data-stu-id="4a822-104">For each organization that offers benefits, you must configure settings for benefits confirmation emails.</span></span>

## <a name="configure-confirmation-email-settings"></a><span data-ttu-id="4a822-105">Konfigurera e-postinställningar för bekräftelse</span><span class="sxs-lookup"><span data-stu-id="4a822-105">Configure confirmation email settings</span></span>

1. <span data-ttu-id="4a822-106">I arbetsytan **Förmånshantering** under **inställningar**, välj **Personalparametrar**.</span><span class="sxs-lookup"><span data-stu-id="4a822-106">In the **Benefits management** workspace, under **Setup**, select **Human Resources Parameters**.</span></span>

2. <span data-ttu-id="4a822-107">På fliken **Hantering av förmåner**, ange värden för följande fält:</span><span class="sxs-lookup"><span data-stu-id="4a822-107">In the **Benefits management** tab, specify values for the following fields:</span></span> 

   | <span data-ttu-id="4a822-108">Fält</span><span class="sxs-lookup"><span data-stu-id="4a822-108">Field</span></span> | <span data-ttu-id="4a822-109">beskrivning</span><span class="sxs-lookup"><span data-stu-id="4a822-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="4a822-110">**Skicka bekräftelsemeddelande**</span><span class="sxs-lookup"><span data-stu-id="4a822-110">**Send confirmation email**</span></span> | <span data-ttu-id="4a822-111">När den här funktionen är aktiverad skickas ett e-postmeddelande till medarbetarna när de checkar ut från förmånsanmälan i medarbetarnas självbetjäning.</span><span class="sxs-lookup"><span data-stu-id="4a822-111">When this feature is on, a confirmation email will be sent to employees when they check out from the benefits enrollment experience in Employee self-service.</span></span> |
   | <span data-ttu-id="4a822-112">**Mall för bekräftelsemeddelande**</span><span class="sxs-lookup"><span data-stu-id="4a822-112">**Confirmation email template**</span></span> | <span data-ttu-id="4a822-113">Välj den organisations-e-postmall som du vill använda när du skickar anmälningsbekräftelsen.</span><span class="sxs-lookup"><span data-stu-id="4a822-113">Select the organization email template to use when sending the enrollment confirmation.</span></span> <span data-ttu-id="4a822-114">Om du inte väljer en mall skickas följande allmänna e-postmeddelande:</span><span class="sxs-lookup"><span data-stu-id="4a822-114">If you don't select a template, the following generic email will be sent:</span></span><br><br><span data-ttu-id="4a822-115">%EmployeeFirstName%.</span><span class="sxs-lookup"><span data-stu-id="4a822-115">%EmployeeFirstName%,</span></span><br><br><span data-ttu-id="4a822-116">Grattis!</span><span class="sxs-lookup"><span data-stu-id="4a822-116">Congratulations!</span></span> <span data-ttu-id="4a822-117">Du har slutfört en förmånsanmälan.</span><span class="sxs-lookup"><span data-stu-id="4a822-117">You’ve successfully completed benefits enrollment.</span></span><br><br><span data-ttu-id="4a822-118">Tack</span><span class="sxs-lookup"><span data-stu-id="4a822-118">Thank you,</span></span><br><span data-ttu-id="4a822-119"><Company/Org name> förmåner.</span><span class="sxs-lookup"><span data-stu-id="4a822-119"><Company/Org name> Benefits.</span></span> |
   | <span data-ttu-id="4a822-120">**E-postavsändarens standardadress**</span><span class="sxs-lookup"><span data-stu-id="4a822-120">**Default email sender address**</span></span> | <span data-ttu-id="4a822-121">E-postadressen som ska användas när bekräftelsemeddelandet skickas.</span><span class="sxs-lookup"><span data-stu-id="4a822-121">The email address to use when sending the confirmation email.</span></span> |

3. <span data-ttu-id="4a822-122">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4a822-122">Select **Save**.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]