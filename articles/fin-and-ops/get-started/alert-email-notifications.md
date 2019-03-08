---
title: Klientens notifieringsmeddelanden via e-post
description: Det här avsnittet innehåller information om hur du skapar regler som skickar e-postmeddelanden för fördefinierade händelser.
author: tjvass
manager: AnnBe
ms.date: 02/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: kfend
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2019-1-29
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 314f04eec04a75aed058c9c38066738e8758f653
ms.sourcegitcommit: 440ebe14ad26574ba227d23ee8370f6b6110645b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2019
ms.locfileid: "373828"
---
# <a name="client-alert-notifications-by-email"></a><span data-ttu-id="4040d-103">Klientens notifieringsmeddelanden via e-post</span><span class="sxs-lookup"><span data-stu-id="4040d-103">Client alert notifications by email</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="4040d-104">I Microsoft Dynamics 365 for Finance and Operations kan du definiera anpassade notifieringsregler som övervakar filtrerade vyer av data och skicka e-postmeddelanden automatiskt vid fördefinierade händelser.</span><span class="sxs-lookup"><span data-stu-id="4040d-104">In Microsoft Dynamics 365 for Finance and Operations, you can define custom alert rules that monitor filtered views of data and automatically send email notifications when predefined events occur.</span></span> <span data-ttu-id="4040d-105">Alternativet att skicka e-postmeddelanden är tillgängligt för alla stödda varningstyper och kan även aktiveras för befintliga varningsregler.</span><span class="sxs-lookup"><span data-stu-id="4040d-105">The option to send email notifications is available for all supported alert types and can also be turned on for existing alert rules.</span></span>

<span data-ttu-id="4040d-106">Du kan använda inbyggda kontroller för att skapa notifieringsregler som övervakar filtrerade vyer av batchjobb i systemet.</span><span class="sxs-lookup"><span data-stu-id="4040d-106">You can use built-in controls to create alert rules that monitor the filtered views of system batch jobs.</span></span> <span data-ttu-id="4040d-107">Genom att kontrollera värdet för fältet **Status** kan du konfigurera notifieringsregler som skickar e-post när batch-jobbet misslyckas.</span><span class="sxs-lookup"><span data-stu-id="4040d-107">By monitoring the value of the **Status** field, you can also configure alert rules that send email when a batch job fails.</span></span> <span data-ttu-id="4040d-108">När dessa notifieringsregler skapas, behöver du inte längre kontrollera rapporter för ändringar i affärsdata.</span><span class="sxs-lookup"><span data-stu-id="4040d-108">After these alert rules are created, you no longer have to check reports for changes to business data.</span></span> <span data-ttu-id="4040d-109">I stället kan du låta Finance and Operations intelligent ändra identifieringstjänsten göra övervakningen.</span><span class="sxs-lookup"><span data-stu-id="4040d-109">Instead, you can let the Finance and Operations intelligent change detection service do the monitoring for you.</span></span>

<span data-ttu-id="4040d-110">Klientnotifieringar beror på undersystemet för e-post som tillhandahålls via integrering med Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="4040d-110">Client alerts depend on the email subsystem that is provided through integration with Microsoft Office.</span></span> <span data-ttu-id="4040d-111">Vi rekommenderar att du använder Simple Mail Transfer Protocol (SMTP)-leverantören, så att e-postdistribution inte är beroende av en lokal e-postklient.</span><span class="sxs-lookup"><span data-stu-id="4040d-111">We recommend that you use the Simple Mail Transfer Protocol (SMTP) provider, so that email distribution doesn't have to rely on a local mail client.</span></span>

<span data-ttu-id="4040d-112">Kunder måste konfigurera integrerade e-posttjänster om du vill skicka meddelanden via e-post.</span><span class="sxs-lookup"><span data-stu-id="4040d-112">To send notifications by email, customers must configure integrated email services.</span></span> <span data-ttu-id="4040d-113">E-postmeddelanden skickas till mottagare på uppdrag av notifieringarnas ägare.</span><span class="sxs-lookup"><span data-stu-id="4040d-113">Email notifications are sent to recipients on behalf of alert owners.</span></span>

<span data-ttu-id="4040d-114">För mer information om hur du konfigurerar e-post i Finance and Operation se [konfigurera och skicka e-post](../organization-administration/configure-email.md).</span><span class="sxs-lookup"><span data-stu-id="4040d-114">For more information about how to configure email in Finance and Operations, see [Configure and send email](../organization-administration/configure-email.md).</span></span>

<span data-ttu-id="4040d-115">Följande bild visar dialogrutan **Skapa notifieringsregel** som nu innehåller ett alternativ för **skicka e-post**.</span><span class="sxs-lookup"><span data-stu-id="4040d-115">The following image shows the **Create alert rule** dialog box, which now includes a **Send email** option.</span></span>

<span data-ttu-id="4040d-116">[![Dialogrutan Skapa notifieringsregel alternativet Skicka e-post är inställt på Ja](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)</span><span class="sxs-lookup"><span data-stu-id="4040d-116">[![Create alert rule dialog box, where the Send email option is set to Yes](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)</span></span>

> [!NOTE]
> <span data-ttu-id="4040d-117">När alternativet **skicka e-post** är inställt på **Ja** kommer notifieringar fortsätta levereras från Åtgärdscentret.</span><span class="sxs-lookup"><span data-stu-id="4040d-117">When the **Send email** option is set to **Yes**, alert notifications will continue to be delivered from the Action Center.</span></span>

## <a name="alert-notification-email-templates"></a><span data-ttu-id="4040d-118">E-postmeddelanden med notifieringar</span><span class="sxs-lookup"><span data-stu-id="4040d-118">Alert notification email templates</span></span>

<span data-ttu-id="4040d-119">Tjänsten skickar e-postmeddelanden med hjälp av fördefinierade e-postmallar som ger grundläggande information om varningsmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="4040d-119">The service sends email notifications by using predefined email templates that deliver the basic details of the alert notification.</span></span> <span data-ttu-id="4040d-120">Den här informationen innefattar en direkt länk till sidan där notifieringsregeln har definierats.</span><span class="sxs-lookup"><span data-stu-id="4040d-120">These details include a direct link to the page where the alert rule was defined.</span></span>

<span data-ttu-id="4040d-121">Följande bild visar strukturen för aviseringar skickas när de tas emot via e-post.</span><span class="sxs-lookup"><span data-stu-id="4040d-121">The following image show the structure of the alert notifications when they are received by email.</span></span>

<span data-ttu-id="4040d-122">[![Mallbaserade aviseringar för att skapa, ändra och ta bort mallen](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)</span><span class="sxs-lookup"><span data-stu-id="4040d-122">[![Template-based alert notifications for record creation, field changes, and template deletion](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)</span></span>
