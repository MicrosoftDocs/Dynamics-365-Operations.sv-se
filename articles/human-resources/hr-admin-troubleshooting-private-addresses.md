---
title: Åtkomst till privata adresser per säkerhetsroll
description: Det här avsnittet beskriver hur du löser problemet när en kund kan inte komma åt privata adresser.
author: andreabichsel
manager: tfehr
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6598094e7877a30c35e1b03794f82c8a4ec001a7
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114269"
---
# <a name="access-to-private-addresses-by-security-role"></a><span data-ttu-id="60cae-103">Åtkomst till privata adresser efter säkerhetsroll</span><span class="sxs-lookup"><span data-stu-id="60cae-103">Access to private addresses by security role</span></span>

<span data-ttu-id="60cae-104">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="60cae-104">**Issue**</span></span>

<span data-ttu-id="60cae-105">Efter att en kund duplicerar en säkerhetsroll och loggar in som den nya rollen kan kunden inte se adresser som är märkta som privata.</span><span class="sxs-lookup"><span data-stu-id="60cae-105">After a customer duplicates a security role and signs in as that new role, the customer can't see addresses that were marked as private.</span></span>

<span data-ttu-id="60cae-106">**Upplösning**</span><span class="sxs-lookup"><span data-stu-id="60cae-106">**Resolution**</span></span>

<span data-ttu-id="60cae-107">För att lösa problemet måste kunden följa instruktionerna på den dubblerade säkerhetsrollen.</span><span class="sxs-lookup"><span data-stu-id="60cae-107">To resolve the issue, the customer must follow these steps for the duplicated security role.</span></span>

1. <span data-ttu-id="60cae-108">Gå till **Organisationsadministration \> Global adressbok \> Parametrar för global adressbok**.</span><span class="sxs-lookup"><span data-stu-id="60cae-108">Go to **Organization administration \> Global address book \> Global address book parameters**.</span></span>
2. <span data-ttu-id="60cae-109">På fliken **Säkerhet för privat plats** och flytta den nya rollen från listan **Tillgängliga roller** till listan **Markerade roller**.</span><span class="sxs-lookup"><span data-stu-id="60cae-109">On the **Private location security** tab, move the new security role from the **Available roles** list to the **Selected roles** list.</span></span>
3. <span data-ttu-id="60cae-110">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="60cae-110">Select **Save**.</span></span>

![Sidan Parametrar för global adressbok](media/GAD-parameters.png)
