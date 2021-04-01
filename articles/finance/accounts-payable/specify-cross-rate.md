---
title: Ange valutakurs
description: Det här ämnet innehåller information om valutakurser i Microsoft Dynamics 365 Finance.
author: abruer
manager: AnnBe
ms.date: 05/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a1463b9676e6b26543fd88607ca13b0ceb12be5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231576"
---
# <a name="specify-the-cross-rate"></a><span data-ttu-id="72706-103">Ange valutakurs</span><span class="sxs-lookup"><span data-stu-id="72706-103">Specify the cross rate</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="72706-104">Det här avsnittet beskriver syftet med en växlingskurs och hur du anger växlingskursen när du kvittar en betalning mot en faktura.</span><span class="sxs-lookup"><span data-stu-id="72706-104">This topic explains the purpose of a cross rate, and how to specify the cross rate when you settle a payment with an invoice.</span></span> <span data-ttu-id="72706-105">Använd en växlingskurs när alla följande villkor gäller:</span><span class="sxs-lookup"><span data-stu-id="72706-105">Use a cross rate when all of the following criteria apply:</span></span> 
-   <span data-ttu-id="72706-106">Du kvittar en betalning mot en faktura.</span><span class="sxs-lookup"><span data-stu-id="72706-106">You are settling a payment with an invoice.</span></span> 
-   <span data-ttu-id="72706-107">Betalningsraden och fakturaraden använder olika valutor.</span><span class="sxs-lookup"><span data-stu-id="72706-107">The payment line and the invoice line use different currencies.</span></span> 
-   <span data-ttu-id="72706-108">Ingen av valutorna är redovisningsvalutan.</span><span class="sxs-lookup"><span data-stu-id="72706-108">Neither currency is the accounting currency.</span></span> 

<span data-ttu-id="72706-109">Växlingskursen används inte för att beräkna valutaregistrering för betalningstransaktionen till betalningens redovisningsvaluta.</span><span class="sxs-lookup"><span data-stu-id="72706-109">The cross rate is not used to calculate the payment transaction currency translation to the payment accounting currency.</span></span> <span data-ttu-id="72706-110">I stället hämtas valutakurser från valutakurstabellerna för att beräkna värdet på betalningstransaktionens valutabelopp och betalningsredovisningens valutabelopp.</span><span class="sxs-lookup"><span data-stu-id="72706-110">Instead, the exchange rates from the exchange rate tables are retrieved to calculate the value of the payment transaction currency amount and the payment accounting currency amount.</span></span> 

<span data-ttu-id="72706-111">Redovisningsvalutan är till exempel USD, fakturavalutan CAD och betalningsvalutan EUR.</span><span class="sxs-lookup"><span data-stu-id="72706-111">For example, the accounting currency is USD, the invoice currency is CAD, and the payment currency is EUR.</span></span> <span data-ttu-id="72706-112">Med växlingskursen kan du ange en valutakurs för att översätta direkt mellan CAD och EUR utan att behöva översätta via USD.</span><span class="sxs-lookup"><span data-stu-id="72706-112">The cross rate lets you enter an exchange rate to translate directly between CAD and EUR, and not have to translate through USD.</span></span> <span data-ttu-id="72706-113">När du väljer en faktura och en primär betalning, kan du ange en växlingskurs för fakturaraden.</span><span class="sxs-lookup"><span data-stu-id="72706-113">When you select an invoice and a primary payment, you can enter a cross rate for the invoice line.</span></span> <span data-ttu-id="72706-114">Växlingskursen är valutakursen mellan valutorna för dessa transaktioner på kvittningsdatumet.</span><span class="sxs-lookup"><span data-stu-id="72706-114">The cross rate is the exchange rate between the currencies for those transactions, as of the settlement date.</span></span>

1.  <span data-ttu-id="72706-115">Gå till en av följande sidor:</span><span class="sxs-lookup"><span data-stu-id="72706-115">Go to one of the following pages:</span></span>
- <span data-ttu-id="72706-116">**Kundreskontra > Allmänt > Kunder > Alla kunder**</span><span class="sxs-lookup"><span data-stu-id="72706-116">**Accounts receivable > Common > Customers > All customers**</span></span> 
- <span data-ttu-id="72706-117">**Leverantörsreskontra > Allmänt > Leverantörer > Alla leverantörer**</span><span class="sxs-lookup"><span data-stu-id="72706-117">**Accounts payable > Common > Vendors > All vendors**</span></span> 
- <span data-ttu-id="72706-118">**Anskaffning och källa > Allmänt > Leverantörer > Alla leverantörer.**</span><span class="sxs-lookup"><span data-stu-id="72706-118">**Procurement and sourcing > Common > Vendors > All vendors**</span></span>
2.  <span data-ttu-id="72706-119">Välj kunden eller leverantören som du kvittar öppna transaktioner för.</span><span class="sxs-lookup"><span data-stu-id="72706-119">Select the customer or vendor whose open transactions you are settling.</span></span> 
3.  <span data-ttu-id="72706-120">För en kund, på listsidan **Alla kunder**, gå till **Samla in > Kvitta öppna transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="72706-120">For a customer, on the **All customers** list page, go to **Collect > Settle open transactions**.</span></span> <span data-ttu-id="72706-121">För en leverantör, på listsidan **Alla leverantörer**, gå till **Faktura > Kvitta öppna transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="72706-121">For a vendor, on the **All vendors** list page, go to **Invoice > Settle open transactions**.</span></span> 
4.  <span data-ttu-id="72706-122">Välj transaktionen som är den primära betalningen och klicka på **Markera betalning**.</span><span class="sxs-lookup"><span data-stu-id="72706-122">Select the transaction that is the primary payment, and then click **Mark payment**.</span></span> <span data-ttu-id="72706-123">Kryssrutan i kolumnen **Markera** markeras och en informationsikon visas i kolumnen **Primär betalning**.</span><span class="sxs-lookup"><span data-stu-id="72706-123">The check box in the **Mark** column is selected, and an information icon is shown in the **Primary payment** column.</span></span> 
5.  <span data-ttu-id="72706-124">I fältet **Växlingskurs** ange valutakursen mellan fakturavalutan och betalningsvalutan, på kvittningsdatumet.</span><span class="sxs-lookup"><span data-stu-id="72706-124">In the **Cross rate** field, enter the exchange rate between the invoice currency and the payment currency, as of the settlement date.</span></span> 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]