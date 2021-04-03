---
title: Felsöka Dynamics 365-betalningskoppling för Adyen-problem
description: Det här ämnet ger felsökningsvägledning som kan hjälpa dig att få support när du har problem med Microsoft Dynamics 365 Payment Connector för Adyen.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f01db3fa670355696c094be544775a3abc557a70
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585530"
---
# <a name="troubleshoot-dynamics-365-payment-connector-for-adyen-issues"></a><span data-ttu-id="0bc9c-103">Felsöka Dynamics 365-betalningskoppling för Adyen-problem</span><span class="sxs-lookup"><span data-stu-id="0bc9c-103">Troubleshoot Dynamics 365 Payment Connector for Adyen issues</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0bc9c-104">Det här ämnet ger felsökningsvägledning som kan hjälpa dig att få support när du har problem med Microsoft Dynamics 365 Payment Connector för Adyen.</span><span class="sxs-lookup"><span data-stu-id="0bc9c-104">This topic provides troubleshooting guidance that can help you get support when you have issues with the Microsoft Dynamics 365 Payment Connector for Adyen.</span></span>

## <a name="description"></a><span data-ttu-id="0bc9c-105">beskrivning</span><span class="sxs-lookup"><span data-stu-id="0bc9c-105">Description</span></span>

<span data-ttu-id="0bc9c-106">Det finns problem med Dynamics 365 Payment Connector för Adyen inom följande områden, och du behöver stöd från Adyen-teamet:</span><span class="sxs-lookup"><span data-stu-id="0bc9c-106">You have issues with the Dynamics 365 Payment Connector for Adyen in the following areas, and you require support from the Adyen team:</span></span>

- <span data-ttu-id="0bc9c-107">Konfiguration av Point of sale (POS), Modern point of sale (MPOS), kundtjänst eller Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="0bc9c-107">Configuration of Point of sale (POS), Modern point of sale (MPOS), call center, or Dynamics 365 Commerce</span></span>
- <span data-ttu-id="0bc9c-108">Adyen tjänsteleverantör för betalning (PSP) referensnummer (till exempel om du har frågor om avslag, inklusive manuell nyckelinmatning \[MKE\] avslag)</span><span class="sxs-lookup"><span data-stu-id="0bc9c-108">The Adyen payment service provider (PSP) reference number (for example, if you have questions about refusals, including manual key entry \[MKE\] refusals)</span></span>
- <span data-ttu-id="0bc9c-109">Allt som inte fungerar i test- eller live handelsmiljöer</span><span class="sxs-lookup"><span data-stu-id="0bc9c-109">Anything that isn't working in test or live merchant environments</span></span>

## <a name="resolution"></a><span data-ttu-id="0bc9c-110">Upplösning</span><span class="sxs-lookup"><span data-stu-id="0bc9c-110">Resolution</span></span>

<span data-ttu-id="0bc9c-111">Använd följande e-postmall för att starta supportprocessen med Adyen-team.</span><span class="sxs-lookup"><span data-stu-id="0bc9c-111">Use the following email template to start the support process with the Adyen team.</span></span> <span data-ttu-id="0bc9c-112">När du vill felsöka bör du se till att e-postmeddelandet innehåller all information som behövs.</span><span class="sxs-lookup"><span data-stu-id="0bc9c-112">To expedite troubleshooting, make sure that the email contains all the required details.</span></span>

| <span data-ttu-id="0bc9c-113">Fält</span><span class="sxs-lookup"><span data-stu-id="0bc9c-113">Field</span></span>        | <span data-ttu-id="0bc9c-114">Värde</span><span class="sxs-lookup"><span data-stu-id="0bc9c-114">Value</span></span> |
|--------------|-------|
| <span data-ttu-id="0bc9c-115">Till</span><span class="sxs-lookup"><span data-stu-id="0bc9c-115">To</span></span>           | `support@adyen.com` |
| <span data-ttu-id="0bc9c-116">Kopia</span><span class="sxs-lookup"><span data-stu-id="0bc9c-116">Cc</span></span>           | |
| <span data-ttu-id="0bc9c-117">Ämnesrad</span><span class="sxs-lookup"><span data-stu-id="0bc9c-117">Subject line</span></span> | <span data-ttu-id="0bc9c-118">Supportförfrågan Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="0bc9c-118">Microsoft Dynamics Support Request</span></span> |
| <span data-ttu-id="0bc9c-119">Brödtext</span><span class="sxs-lookup"><span data-stu-id="0bc9c-119">Body</span></span>         | <p><span data-ttu-id="0bc9c-120">Hej support,</span><span class="sxs-lookup"><span data-stu-id="0bc9c-120">Hi Support,</span></span></p><p><span data-ttu-id="0bc9c-121">Ge stöd för följande problem:</span><span class="sxs-lookup"><span data-stu-id="0bc9c-121">Please provide support for the following issue:</span></span></p><ul><li><span data-ttu-id="0bc9c-122">Handlarkonto</span><span class="sxs-lookup"><span data-stu-id="0bc9c-122">Merchant account</span></span></li><li><span data-ttu-id="0bc9c-123">Miljö (Test/Prod)</span><span class="sxs-lookup"><span data-stu-id="0bc9c-123">Environment (Test/Prod)</span></span></li><li><span data-ttu-id="0bc9c-124">Kanal (POS/kundtjänst/e-handel)</span><span class="sxs-lookup"><span data-stu-id="0bc9c-124">Channel (POS/call center/Commerce e-commerce)</span></span></li><li><span data-ttu-id="0bc9c-125">PSP referensnummer om problemet ingår i en specifik transaktion (Du kan hitta PSP-referensnumret på kvittot, i Adyen kundområde eller på transaktionsmenyn i kassaterminalen.)</span><span class="sxs-lookup"><span data-stu-id="0bc9c-125">PSP reference number, if the issue involved a specific transaction (You can find the PSP reference number on the receipt, in the Adyen Customer Area, or on the transactions menu on the POS terminal.)</span></span></li><li><span data-ttu-id="0bc9c-126">Skärmdump eller bild av felmeddelandet, om det är tillämpligt</span><span class="sxs-lookup"><span data-stu-id="0bc9c-126">Screenshot or photo of the error message, if applicable</span></span></li><li><span data-ttu-id="0bc9c-127">Loggfiler för Loggboken (i .txt-format)</span><span class="sxs-lookup"><span data-stu-id="0bc9c-127">Event Viewer logs (in .txt format)</span></span></li><li><span data-ttu-id="0bc9c-128">Beskrivning av det problem och de felsökningssteg du har försökt</span><span class="sxs-lookup"><span data-stu-id="0bc9c-128">Description of the issue and troubleshooting steps that you've tried</span></span></li></ul> |

## <a name="additional-resources"></a><span data-ttu-id="0bc9c-129">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="0bc9c-129">Additional resources</span></span>

[<span data-ttu-id="0bc9c-130">Acceptera betalningar med Adyen-kopplingen för Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="0bc9c-130">Accept payments with the Adyen connector for Dynamics 365 Commerce</span></span>](https://www.adyen.com/partners/dynamics-365-commerce)

[<span data-ttu-id="0bc9c-131">Dynamics 365-betalningskoppling för Adyen</span><span class="sxs-lookup"><span data-stu-id="0bc9c-131">Dynamics 365 Payment Connector for Adyen</span></span>](../dev-itpro/adyen-connector.md)

[<span data-ttu-id="0bc9c-132">Ställ in Adyen betalningskoppling för Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="0bc9c-132">Set up the Adyen payment connector for Dynamics 365</span></span>](https://docs.adyen.com/plugins/microsoft-dynamics)
