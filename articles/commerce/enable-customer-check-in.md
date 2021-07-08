---
title: Aktivera incheckningsmeddelanden för kunder i kassan (POS)
description: I det här ämnet beskrivs hur du aktiverar incheckningsmeddelanden för kunder Microsoft Dynamics 365 Commerce i kassan (POS).
author: bicyclingfool
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: b42dc7766f8a69a7409c28d21b49cc96eca18dd4
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271435"
---
# <a name="enable-customer-check-in-notifications-in-point-of-sale-pos"></a><span data-ttu-id="a19d2-103">Aktivera incheckningsmeddelanden för kunder i kassan (POS)</span><span class="sxs-lookup"><span data-stu-id="a19d2-103">Enable customer check-in notifications in point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a19d2-104">I det här ämnet beskrivs hur du aktiverar incheckningsmeddelanden för kunder Microsoft Dynamics 365 Commerce i kassan (POS).</span><span class="sxs-lookup"><span data-stu-id="a19d2-104">This topic describes how to enable customer check-in notifications in Microsoft Dynamics 365 Commerce point of sale (POS).</span></span>

<span data-ttu-id="a19d2-105">I sina "order redo för hämtning"-meddelanden via e-post kan organisationer skicka med en länk eller knapp som låter kunderna meddela butiken att de är på plats och väntar på att deras paket ska hämtas ut till dem.</span><span class="sxs-lookup"><span data-stu-id="a19d2-105">In their "order ready for pickup" emails, organizations can provide a link or button that lets customers notify the store that they are on the premises and waiting for their package to be brought out to them.</span></span> <span data-ttu-id="a19d2-106">Kunderna får sedan en incheckningsbekräftelse och butiken ett meddelande som en uppgift i sitt kassaprogram.</span><span class="sxs-lookup"><span data-stu-id="a19d2-106">Customers then receive a check-in confirmation, and the store receives a notification as a task in its POS application.</span></span> <span data-ttu-id="a19d2-107">Denna uppgift fungerar som en uppmaning till en försäljare att leverera ordern till kundens fordon.</span><span class="sxs-lookup"><span data-stu-id="a19d2-107">This task serves as a prompt for a sales associate to deliver the order to the customer's vehicle.</span></span> <span data-ttu-id="a19d2-108">Därför behöver kunden inte komma in i butiken.</span><span class="sxs-lookup"><span data-stu-id="a19d2-108">Therefore, the customer doesn't have to enter the store.</span></span>

<span data-ttu-id="a19d2-109">Kundens incheckningsarbetsflöde kan även konfigureras för att samla in ytterligare information från kunder, till exempel deras nummer på parkeringsplatsen, fordonets märk, modell och färg, samt leveransinstruktioner.</span><span class="sxs-lookup"><span data-stu-id="a19d2-109">The customer check-in workflow can also be configured to collect additional information from customers, such as their parking spot number, the make, model, and color of their vehicle, and delivery instructions.</span></span> <span data-ttu-id="a19d2-110">Butiken kan använda den här informationen för att underlätta orderuppfyllelsen.</span><span class="sxs-lookup"><span data-stu-id="a19d2-110">The retail store attendant can use this information to facilitate order fulfillment.</span></span>

## <a name="enable-customer-check-in"></a><span data-ttu-id="a19d2-111">Aktivera incheckning för kund</span><span class="sxs-lookup"><span data-stu-id="a19d2-111">Enable customer check-in</span></span>

<span data-ttu-id="a19d2-112">När incheckningsfunktionen för kund är aktiverad genererar Commerce ett orderbekräftelse-ID (även kallat kanalreferens-ID).</span><span class="sxs-lookup"><span data-stu-id="a19d2-112">When the customer check-in feature is turned on, Commerce generates an order confirmation ID (also known as the channel reference ID).</span></span> <span data-ttu-id="a19d2-113">Det genererar även orderbekräftelse-ID för order som skapas via kassakanaler (POS) eller kundtjänstkanaler.</span><span class="sxs-lookup"><span data-stu-id="a19d2-113">It also generates order confirmation IDs for orders that are created through point of sale (POS) or call center channels.</span></span> 

<span data-ttu-id="a19d2-114">Följ dessa steg om du vill aktivera incheckningsfunktionen för kund i Commerce-administrationen.</span><span class="sxs-lookup"><span data-stu-id="a19d2-114">To turn on the customer check-in feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="a19d2-115">Gå till **Arbetsytor \> Funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="a19d2-115">Go to **Workspaces \> Feature management**.</span></span>
2. <span data-ttu-id="a19d2-116">Sök efter funktionen **Generera ID-format för konsekvent kanalreferens för flera kanaler**.</span><span class="sxs-lookup"><span data-stu-id="a19d2-116">Search for the **Generate a consistent channel reference ID format across channels** feature.</span></span> 
3. <span data-ttu-id="a19d2-117">Välj funktionen och sedan **Aktivera nu** i egenskapsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a19d2-117">Select the feature, and then select **Enable now** in the properties pane.</span></span> 

## <a name="create-a-check-in-confirmation-page"></a><span data-ttu-id="a19d2-118">Skapa en bekräftelsesida för incheckning</span><span class="sxs-lookup"><span data-stu-id="a19d2-118">Create a check-in confirmation page</span></span>

<span data-ttu-id="a19d2-119">På din näthandelsplats måste du skapa en ny sida som fungerar som upplevelse för incheckningsbekräftelse.</span><span class="sxs-lookup"><span data-stu-id="a19d2-119">On your e-commerce site, you must create a new page that will serve as the check-in confirmation experience.</span></span> <span data-ttu-id="a19d2-120">Genom ytterligare konfiguration kan sidan även innehålla ett formulär som samlar in ytterligare information från kunder i syfte att underlätta uppfyllelsen av order.</span><span class="sxs-lookup"><span data-stu-id="a19d2-120">Through additional configuration, the page can also include a form that collects additional information from customers to facilitate order fulfillment.</span></span> <span data-ttu-id="a19d2-121">Information om hur du ställer in sida och modul finns i [modulen Kundincheckning](check-in-pickup-module.md).</span><span class="sxs-lookup"><span data-stu-id="a19d2-121">For information about how to set up the page and module, see [Customer check-in module](check-in-pickup-module.md).</span></span>

## <a name="configure-the-transactional-email-template"></a><span data-ttu-id="a19d2-122">Konfigurera mallen för transaktionsmeddelande via e-post</span><span class="sxs-lookup"><span data-stu-id="a19d2-122">Configure the transactional email template</span></span>

<span data-ttu-id="a19d2-123">Du måste lägga till en **Jag är här**-länk eller -knapp till mallen för det transaktionsmeddelande via e-post som kunderna erhåller när deras order är redo för hämtning.</span><span class="sxs-lookup"><span data-stu-id="a19d2-123">You must add an **I am here** link or button to the template for the transactional email that customers receive when their order is ready for pickup.</span></span> <span data-ttu-id="a19d2-124">Kunderna använder den här länken eller knappen när de meddelar butiken om att de har anlänt för att hämta sin order.</span><span class="sxs-lookup"><span data-stu-id="a19d2-124">Customers will use this link or button to notify the store that they have arrived to pick up their order.</span></span> 

<span data-ttu-id="a19d2-125">Lägg till länken eller knappen i mallen som är mappad till meddelandetypen **Packning slutförd** samt det leveransläge som du använder för drive in-leverans.</span><span class="sxs-lookup"><span data-stu-id="a19d2-125">Add the link or button to the template that is mapped to the **Packing completed** notification type and the mode of delivery that you're using for curbside order fulfillment.</span></span> <span data-ttu-id="a19d2-126">Skapa en HTML-länk eller -knapp i mallen som pekar på URL-adressen till den incheckningsbekräftelsesida som du skapat.</span><span class="sxs-lookup"><span data-stu-id="a19d2-126">In the template, create an HTML link or button that points to the URL of the check-in confirmation page that you created.</span></span> <span data-ttu-id="a19d2-127">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="a19d2-127">Here is an example.</span></span>

```
<a href="https://[YOUR_SITE_DOMAIN]/[CHECK-IN_CONFIRMATION_PAGE]?channelReferenceId=%channelreferenceid%&channelId=%channelid%&packingSlipId=%packingslipid%" target="_blank">I am here!</a>
```
<span data-ttu-id="a19d2-128">Mer information om hur du konfigurerar e-postmallar finns i [Anpassa transaktionella e-postmeddelanden per leveranssätt](customize-email-delivery-mode.md).</span><span class="sxs-lookup"><span data-stu-id="a19d2-128">For more information about how to configure email templates, see [Customize transactional emails by mode of delivery](customize-email-delivery-mode.md).</span></span> 

## <a name="a-check-in-confirmation-task-is-created-in-pos"></a><span data-ttu-id="a19d2-129">En incheckningsbekräftelseuppgift skapas i kassan (POS)</span><span class="sxs-lookup"><span data-stu-id="a19d2-129">A check-in confirmation task is created in POS</span></span>

<span data-ttu-id="a19d2-130">När en kund har meddelat butiken att de har anlänt för en avhämtning får han eller hon ett meddelande om incheckningsbekräftelse, och en uppgift skapas i uppgiftslistan i kassan (POS) för butiken där kunden hämtar ordern.</span><span class="sxs-lookup"><span data-stu-id="a19d2-130">After a customer notifies the store that they are present for pickup, they receive a check-in confirmation notification, and a task is created in the tasks list in POS for the store where the customer is picking up the order.</span></span> <span data-ttu-id="a19d2-131">Uppgiften innehåller all kund- och orderinformation som krävs för att ordern ska kunna uppfyllas.</span><span class="sxs-lookup"><span data-stu-id="a19d2-131">The task contains all the customer and order information that is required to fulfill the order.</span></span> <span data-ttu-id="a19d2-132">I uppgiften visar instruktionerna i fältet all information som har samlats in från kunden via formuläret för ytterligare information.</span><span class="sxs-lookup"><span data-stu-id="a19d2-132">In the task, the instructions field shows any information that was collected from the customer through the additional information form.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="a19d2-133">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="a19d2-133">Additional resources</span></span>

[<span data-ttu-id="a19d2-134">Incheckning för upphämtningsmodul</span><span class="sxs-lookup"><span data-stu-id="a19d2-134">Check-in for pickup module</span></span>](check-in-pickup-module.md)
