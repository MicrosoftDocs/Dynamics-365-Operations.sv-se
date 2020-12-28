---
title: Konfigurera parametrar för förmånshantering per företag
description: Konfigurera parametrar för förmånshantering per företag i Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2943d0095e4c9421725b90e579b7cbb841038ab7
ms.sourcegitcommit: fd097f6f76f0d8428038fa3655b3188bf093b517
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/08/2020
ms.locfileid: "4692755"
---
# <a name="configure-benefits-management-parameters-per-company"></a><span data-ttu-id="6d69e-103">Konfigurera parametrar för förmånshantering per företag</span><span class="sxs-lookup"><span data-stu-id="6d69e-103">Configure Benefits management parameters per company</span></span>

<span data-ttu-id="6d69e-104">För varje organisation som erbjuder förmåner måste du konfigurera inställningar för förmånsbekräftelsemeddelanden.</span><span class="sxs-lookup"><span data-stu-id="6d69e-104">For each organization that offers benefits, you must configure settings for benefits confirmation emails.</span></span>

## <a name="configure-confirmation-email-settings"></a><span data-ttu-id="6d69e-105">Konfigurera e-postinställningar för bekräftelse</span><span class="sxs-lookup"><span data-stu-id="6d69e-105">Configure confirmation email settings</span></span>

1. <span data-ttu-id="6d69e-106">I arbetsytan **Förmånshantering** under **inställningar**, välj **Personalparametrar**.</span><span class="sxs-lookup"><span data-stu-id="6d69e-106">In the **Benefits management** workspace, under **Setup**, select **Human Resources Parameters**.</span></span>

2. <span data-ttu-id="6d69e-107">På fliken **Hantering av förmåner**, ange värden för följande fält:</span><span class="sxs-lookup"><span data-stu-id="6d69e-107">In the **Benefits management** tab, specify values for the following fields:</span></span> 

   | <span data-ttu-id="6d69e-108">Fält</span><span class="sxs-lookup"><span data-stu-id="6d69e-108">Field</span></span> | <span data-ttu-id="6d69e-109">beskrivning</span><span class="sxs-lookup"><span data-stu-id="6d69e-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="6d69e-110">**Skicka bekräftelsemeddelande**</span><span class="sxs-lookup"><span data-stu-id="6d69e-110">**Send confirmation email**</span></span> | <span data-ttu-id="6d69e-111">När den här funktionen är aktiverad skickas ett e-postmeddelande till medarbetarna när de checkar ut från förmånsanmälan i medarbetarnas självbetjäning.</span><span class="sxs-lookup"><span data-stu-id="6d69e-111">When this feature is on, a confirmation email will be sent to employees when they check out from the benefits enrollment experience in Employee self-service.</span></span> |
   | <span data-ttu-id="6d69e-112">**Mall för bekräftelsemeddelande**</span><span class="sxs-lookup"><span data-stu-id="6d69e-112">**Confirmation email template**</span></span> | <span data-ttu-id="6d69e-113">Välj den organisations-e-postmall som du vill använda när du skickar anmälningsbekräftelsen.</span><span class="sxs-lookup"><span data-stu-id="6d69e-113">Select the organization email template to use when sending the enrollment confirmation.</span></span> <span data-ttu-id="6d69e-114">Om du inte väljer en mall skickas följande allmänna e-postmeddelande:</span><span class="sxs-lookup"><span data-stu-id="6d69e-114">If you don't select a template, the following generic email will be sent:</span></span><br><br><span data-ttu-id="6d69e-115">%EmployeeFirstName%,</span><span class="sxs-lookup"><span data-stu-id="6d69e-115">%EmployeeFirstName%,</span></span><br><br><span data-ttu-id="6d69e-116">Grattis!</span><span class="sxs-lookup"><span data-stu-id="6d69e-116">Congratulations!</span></span> <span data-ttu-id="6d69e-117">Du har slutfört en förmånsanmälan.</span><span class="sxs-lookup"><span data-stu-id="6d69e-117">You’ve successfully completed benefits enrollment.</span></span><br><br><span data-ttu-id="6d69e-118">Tack</span><span class="sxs-lookup"><span data-stu-id="6d69e-118">Thank you,</span></span><br><span data-ttu-id="6d69e-119"><Company/Org name> förmåner.</span><span class="sxs-lookup"><span data-stu-id="6d69e-119"><Company/Org name> Benefits.</span></span> |
   | <span data-ttu-id="6d69e-120">**E-postavsändarens standardadress**</span><span class="sxs-lookup"><span data-stu-id="6d69e-120">**Default email sender address**</span></span> | <span data-ttu-id="6d69e-121">E-postadressen som ska användas när bekräftelsemeddelandet skickas.</span><span class="sxs-lookup"><span data-stu-id="6d69e-121">The email address to use when sending the confirmation email.</span></span> |

3. <span data-ttu-id="6d69e-122">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6d69e-122">Select **Save**.</span></span>