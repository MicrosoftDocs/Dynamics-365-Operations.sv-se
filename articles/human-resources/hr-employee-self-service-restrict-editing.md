---
title: Begränsa redigering av personlig information
description: Hindra medarbetare från att redigera kontaktinformation i Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6e43b9127b247fa618558b725837d12bf290662f
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052035"
---
# <a name="restrict-editing-of-personal-information"></a><span data-ttu-id="61517-103">Begränsa redigering av personlig information</span><span class="sxs-lookup"><span data-stu-id="61517-103">Restrict editing of personal information</span></span>

[!include [applies to](../includes/applies-to-hr.md)]
[!include [preview feature](./includes/preview-feature.md)]

<span data-ttu-id="61517-104">I det här avsnittet beskrivs hur du begränsar medarbetare från att redigera kontaktinformation i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="61517-104">This topic describes how to restrict employees from editing contact details in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="61517-105">Du kanske vill hindra medarbetarna från att redigera vissa kontaktuppgifter, till exempel deras företagsadress eller e-postadress.</span><span class="sxs-lookup"><span data-stu-id="61517-105">You might want to prevent employees from editing certain contact details, such as their business location or email address.</span></span>

> [!NOTE]
> <span data-ttu-id="61517-106">Om du vill använda funktionen måste du först aktivera **(förhandsversion) begränsa anställda från att lägga till eller redigera adress- och kontaktinformation för utvalda syften** i Funktionshantering.</span><span class="sxs-lookup"><span data-stu-id="61517-106">To use this feature, you must first enable **(Preview) Restrict employees from adding or editing address and contact information for select purposes** in Feature management.</span></span> <span data-ttu-id="61517-107">Mer information om hur du aktiverar förhandsfunktioner finns i [Hantera funktioner](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="61517-107">For more information about enabling preview features, see [Manage features](hr-admin-manage-features.md).</span></span><br><br><span data-ttu-id="61517-108">![Aktivera förhandsversionsfunktion](./media/hr-employee-self-service-restrict-enable.png)</span><span class="sxs-lookup"><span data-stu-id="61517-108">![Enable preview feature](./media/hr-employee-self-service-restrict-enable.png)</span></span>

## <a name="choose-the-information-an-employee-can-add-or-edit"></a><span data-ttu-id="61517-109">Välja vilken information en medarbetare kan lägga till eller redigera</span><span class="sxs-lookup"><span data-stu-id="61517-109">Choose the information an employee can add or edit</span></span>

1. <span data-ttu-id="61517-110">I personal, välj **personalhantering**, välj **länkar** och välj sedan **personalparametrar**.</span><span class="sxs-lookup"><span data-stu-id="61517-110">In Human Resources, select **Personnel management**, select **Links**, and then select **Human resources parameters**.</span></span>

   ![Gå till personalparametrar](./media/hr-employee-self-service-human-resources-parameters.png)

2. <span data-ttu-id="61517-112">På sidan **Personalparametrar** väljer du fliken **Självbetjäning för medarbetare**.</span><span class="sxs-lookup"><span data-stu-id="61517-112">On the **Human resources parameters** page, select the **Employee self service** tab.</span></span>

   ![Välj Självbetjäning för medarbetare](./media/hr-employee-self-service-tab.png)

3. <span data-ttu-id="61517-114">På fliken **Självbetjäning för medarbetare**, avmarkera all information i avsnittet **Adress och kontaktinformation** som du inte vill att medarbetare ska lägga till eller redigera.</span><span class="sxs-lookup"><span data-stu-id="61517-114">On the **Employee self service** tab, uncheck all information in the **Address and contact information** section that you don't want employees to add or edit.</span></span> <span data-ttu-id="61517-115">I det här exemplet har vi avmarkerat **affärskontaktinformation**.</span><span class="sxs-lookup"><span data-stu-id="61517-115">In this example, we've unchecked **Business** contact information.</span></span>

   ![Begränsa redigering av affärskontaktinformation](./media/hr-employee-self-service-restrict-business.png)

4. <span data-ttu-id="61517-117">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="61517-117">Select **Save**.</span></span>

   ![Spara ändringar](./media/hr-employee-self-service-restrict-save.png)

## <a name="employee-experience"></a><span data-ttu-id="61517-119">Medarbetarerfarenhet</span><span class="sxs-lookup"><span data-stu-id="61517-119">Employee experience</span></span>

<span data-ttu-id="61517-120">När du har begränsat medarbetarna till att lägga till eller redigera kontaktdetaljer, kan de visa informationen, men det går inte att ändra den.</span><span class="sxs-lookup"><span data-stu-id="61517-120">After you've restricted employees from adding or editing contact details, they can see the information, but can't change it.</span></span>

<span data-ttu-id="61517-121">I det här exemplet, där anställda är begränsade från redigering **affärskontaktinformation** kan de fortfarande se informationen i självbetjäning för anställda:</span><span class="sxs-lookup"><span data-stu-id="61517-121">In this example, where employees are restricted from editing **Business** contact details, they can still see the information in Employee self service:</span></span>

![Visa affärskontaktinformation](./media/hr-employee-self-service-restrict-view.png)

<span data-ttu-id="61517-123">När de väljer kontaktinformation för företaget visas dock fönstret **Redigera adress** visas som skrivskyddat och de kan inte kan inte ändra något av fälten.</span><span class="sxs-lookup"><span data-stu-id="61517-123">However, when they select the business contact details, the **Edit address** pane appears as read-only, and they can't change any of the fields.</span></span>

![Affärskontaktinformation visas som skrivskyddade](./media/hr-employee-self-service-restrict-read-only.png)

<span data-ttu-id="61517-125">Om de dessutom väljer **Lägg till** för att lägga till ny adress kan de inte välja **Affär** från listrutan **Syfte**.</span><span class="sxs-lookup"><span data-stu-id="61517-125">In addition, if they select **Add** to add a new address, they can't select **Business** from the **Purpose** dropdown box.</span></span>

![Medarbetaren kan inte lägga till en företagsadress](./media/hr-employee-self-service-restrict-add.png)

<span data-ttu-id="61517-127">Medarbetare får samma erfarenhet när de väljer **Kontaktinformation** på sidan **Personlig information** och lägger till en ny adress.</span><span class="sxs-lookup"><span data-stu-id="61517-127">Employees get the same experience when they select **Contact details** on the **Personal information** page and add a new address.</span></span> <span data-ttu-id="61517-128">Listrutan **Syfte** visar bara de typer av information som de kan lägga till.</span><span class="sxs-lookup"><span data-stu-id="61517-128">The **Purpose** dropdown box only displays the types of information they can add.</span></span> 

![Medarbetaren kan inte välja verksamhet i listrutan syfte](./media/hr-employee-self-service-restrict-purpose.png)

<span data-ttu-id="61517-130">**Kontaktinformation** visar nu **Syfte** i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="61517-130">**Contact details** now shows **Purpose** in the grid.</span></span>

![Syfte visas i rutnätet kontaktinformation](./media/hr-employee-self-service-restrict-purpose-grid.png)

## <a name="see-also"></a><span data-ttu-id="61517-132">Se även</span><span class="sxs-lookup"><span data-stu-id="61517-132">See also</span></span>

[<span data-ttu-id="61517-133">Ställa in självbetjäning för medarbetare och chef – översikt</span><span class="sxs-lookup"><span data-stu-id="61517-133">Employee and Manager self service overview</span></span>](hr-employee-manager-self-service-overview.md)<br>
[<span data-ttu-id="61517-134">Konfigurera Human Resources-parametrar</span><span class="sxs-lookup"><span data-stu-id="61517-134">Configure Human resources parameters</span></span>](hr-setup-parameters.md)<br>
[<span data-ttu-id="61517-135">Redigera personliga uppgifter</span><span class="sxs-lookup"><span data-stu-id="61517-135">Edit personal information</span></span>](hr-employee-manager-self-service-edit-personal-information.md)