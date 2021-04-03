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
ms.openlocfilehash: 49f9f50b774df8e215c084bbb493a6be9de6b234
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463946"
---
# <a name="access-to-private-addresses-by-security-role"></a><span data-ttu-id="2cb88-103">Åtkomst till privata adresser efter säkerhetsroll</span><span class="sxs-lookup"><span data-stu-id="2cb88-103">Access to private addresses by security role</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="2cb88-104">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="2cb88-104">**Issue**</span></span>

<span data-ttu-id="2cb88-105">Efter att en kund duplicerar en säkerhetsroll och loggar in som den nya rollen kan kunden inte se adresser som är märkta som privata.</span><span class="sxs-lookup"><span data-stu-id="2cb88-105">After a customer duplicates a security role and signs in as that new role, the customer can't see addresses that were marked as private.</span></span>

<span data-ttu-id="2cb88-106">**Upplösning**</span><span class="sxs-lookup"><span data-stu-id="2cb88-106">**Resolution**</span></span>

<span data-ttu-id="2cb88-107">För att lösa problemet måste kunden följa instruktionerna på den dubblerade säkerhetsrollen.</span><span class="sxs-lookup"><span data-stu-id="2cb88-107">To resolve the issue, the customer must follow these steps for the duplicated security role.</span></span>

1. <span data-ttu-id="2cb88-108">Gå till **Organisationsadministration \> Global adressbok \> Parametrar för global adressbok**.</span><span class="sxs-lookup"><span data-stu-id="2cb88-108">Go to **Organization administration \> Global address book \> Global address book parameters**.</span></span>
2. <span data-ttu-id="2cb88-109">På fliken **Säkerhet för privat plats** och flytta den nya rollen från listan **Tillgängliga roller** till listan **Markerade roller**.</span><span class="sxs-lookup"><span data-stu-id="2cb88-109">On the **Private location security** tab, move the new security role from the **Available roles** list to the **Selected roles** list.</span></span>
3. <span data-ttu-id="2cb88-110">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2cb88-110">Select **Save**.</span></span>

![Sidan Parametrar för global adressbok](media/GAD-parameters.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]