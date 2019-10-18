---
title: Klientens notifieringsmeddelanden via e-post
description: Det här avsnittet innehåller information om hur du skapar regler som skickar e-postmeddelanden för fördefinierade händelser.
author: tjvass
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2019-1-29
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: ba92c3dc1debed7e98210168d1a135e2cf567aec
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2191303"
---
# <a name="client-alert-notifications-by-email"></a><span data-ttu-id="1a75e-103">Kundnotifieringar via e-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="1a75e-103">Client alert notifications by email</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="1a75e-104">Du kan du definiera anpassade notifieringsregler som övervakar filtrerade vyer av data och skicka e-postmeddelanden automatiskt vid fördefinierade händelser.</span><span class="sxs-lookup"><span data-stu-id="1a75e-104">You can define custom alert rules that monitor filtered views of data and automatically send email notifications when predefined events occur.</span></span> <span data-ttu-id="1a75e-105">Alternativet att skicka e-postmeddelanden är tillgängligt för alla stödda varningstyper och kan även aktiveras för befintliga varningsregler.</span><span class="sxs-lookup"><span data-stu-id="1a75e-105">The option to send email notifications is available for all supported alert types and can also be turned on for existing alert rules.</span></span>

<span data-ttu-id="1a75e-106">Du kan använda inbyggda kontroller för att skapa notifieringsregler som övervakar filtrerade vyer av batchjobb i systemet.</span><span class="sxs-lookup"><span data-stu-id="1a75e-106">You can use built-in controls to create alert rules that monitor the filtered views of system batch jobs.</span></span> <span data-ttu-id="1a75e-107">Genom att kontrollera värdet för fältet **Status** kan du konfigurera notifieringsregler som skickar e-post när batch-jobbet misslyckas.</span><span class="sxs-lookup"><span data-stu-id="1a75e-107">By monitoring the value of the **Status** field, you can also configure alert rules that send email when a batch job fails.</span></span> <span data-ttu-id="1a75e-108">När dessa notifieringsregler skapas, behöver du inte längre kontrollera rapporter för ändringar i affärsdata.</span><span class="sxs-lookup"><span data-stu-id="1a75e-108">After these alert rules are created, you no longer have to check reports for changes to business data.</span></span> <span data-ttu-id="1a75e-109">I stället kan du låta den intelligenta ändringsidentifieringstjänsten göra övervakningen.</span><span class="sxs-lookup"><span data-stu-id="1a75e-109">Instead, you can let the intelligent change detection service do the monitoring for you.</span></span>

<span data-ttu-id="1a75e-110">Klientnotifieringar beror på undersystemet för e-post som tillhandahålls via integrering med Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="1a75e-110">Client alerts depend on the email subsystem that is provided through integration with Microsoft Office.</span></span> <span data-ttu-id="1a75e-111">Vi rekommenderar att du använder Simple Mail Transfer Protocol (SMTP)-leverantören, så att e-postdistribution inte är beroende av en lokal e-postklient.</span><span class="sxs-lookup"><span data-stu-id="1a75e-111">We recommend that you use the Simple Mail Transfer Protocol (SMTP) provider, so that email distribution doesn't have to rely on a local mail client.</span></span>

<span data-ttu-id="1a75e-112">Kunder måste konfigurera integrerade e-posttjänster om du vill skicka meddelanden via e-post.</span><span class="sxs-lookup"><span data-stu-id="1a75e-112">To send notifications by email, customers must configure integrated email services.</span></span> <span data-ttu-id="1a75e-113">E-postmeddelanden skickas till mottagare på uppdrag av notifieringarnas ägare.</span><span class="sxs-lookup"><span data-stu-id="1a75e-113">Email notifications are sent to recipients on behalf of alert owners.</span></span>

<span data-ttu-id="1a75e-114">För mer information om hur du konfigurerar e-post, se [konfigurera och skicka e-post](../organization-administration/configure-email.md).</span><span class="sxs-lookup"><span data-stu-id="1a75e-114">For more information about how to configure email, see [Configure and send email](../organization-administration/configure-email.md).</span></span>

<span data-ttu-id="1a75e-115">Följande bild visar dialogrutan **Skapa notifieringsregel** som nu innehåller ett alternativ för **skicka e-post**.</span><span class="sxs-lookup"><span data-stu-id="1a75e-115">The following image shows the **Create alert rule** dialog box, which now includes a **Send email** option.</span></span>

<span data-ttu-id="1a75e-116">[![Dialogrutan Skapa notifieringsregel alternativet Skicka e-post är inställt på Ja](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)</span><span class="sxs-lookup"><span data-stu-id="1a75e-116">[![Create alert rule dialog box, where the Send email option is set to Yes](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)</span></span>

> [!NOTE]
> <span data-ttu-id="1a75e-117">När alternativet **skicka e-post** är inställt på **Ja** kommer notifieringar fortsätta levereras från Åtgärdscentret.</span><span class="sxs-lookup"><span data-stu-id="1a75e-117">When the **Send email** option is set to **Yes**, alert notifications will continue to be delivered from the Action Center.</span></span>

## <a name="alert-notification-email-templates"></a><span data-ttu-id="1a75e-118">E-postmeddelanden med notifieringar</span><span class="sxs-lookup"><span data-stu-id="1a75e-118">Alert notification email templates</span></span>

<span data-ttu-id="1a75e-119">Tjänsten skickar e-postmeddelanden med hjälp av fördefinierade e-postmallar som ger grundläggande information om varningsmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="1a75e-119">The service sends email notifications by using predefined email templates that deliver the basic details of the alert notification.</span></span>

<span data-ttu-id="1a75e-120">Följande bild visar strukturen för aviseringar skickas när de tas emot via e-post.</span><span class="sxs-lookup"><span data-stu-id="1a75e-120">The following image show the structure of the alert notifications when they are received by email.</span></span>

<span data-ttu-id="1a75e-121">[![Mallbaserade aviseringar för att skapa, ändra och ta bort mallen](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)</span><span class="sxs-lookup"><span data-stu-id="1a75e-121">[![Template-based alert notifications for record creation, field changes, and template deletion](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)</span></span>
