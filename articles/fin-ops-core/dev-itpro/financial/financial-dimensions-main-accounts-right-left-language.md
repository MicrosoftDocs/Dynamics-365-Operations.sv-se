---
title: Ekonomiska dimensioner och huvudkonton i språk som skrivs från höger till vänster
description: Det här ämnet beskriver besluten som du bör göra när du använder ett språk som skrivs från höger till vänster och du måste ställa in ekonomiska dimensioner och huvudkontona.
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: rhaertle
ms.custom: 222564
ms.assetid: 875dcebb-1bbb-4841-a8c6-9e134da07e96
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 496869bd3e7a372a5ec791df66fb7a8c43ccad13
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561010"
---
# <a name="financial-dimensions-and-main-accounts-in-right-to-left-languages"></a><span data-ttu-id="ea03b-103">Ekonomiska dimensioner och huvudkonton i språk som skrivs från höger till vänster</span><span class="sxs-lookup"><span data-stu-id="ea03b-103">Financial dimensions and main accounts in right-to-left languages</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ea03b-104">Det här ämnet beskriver några av implementeringsbesluten som du bör beakta när du använder ett språk som skrivs från höger till vänster och du måste ställa in ekonomiska dimensioner och huvudkontona.</span><span class="sxs-lookup"><span data-stu-id="ea03b-104">This topic describes some of the implementation decisions that you should consider when you use a right-to-left language, and you must set up financial dimensions and main accounts.</span></span>

<span data-ttu-id="ea03b-105">Ekonomiska dimensioner och huvudkonton är viktiga komponenter av planeringsfasen för en implementering.</span><span class="sxs-lookup"><span data-stu-id="ea03b-105">Financial dimensions and main accounts are key components of the planning phase for an implementation.</span></span> <span data-ttu-id="ea03b-106">Efter att de ekonomiska dimensionerna och huvudkontona har skapats i systemet, används de på sidorna **Konfigurera kontostrukturer**, **Avancerade regelstrukturer** och **Konfiguration av ekonomisk dimension för integrering av applikationer**.</span><span class="sxs-lookup"><span data-stu-id="ea03b-106">After financial dimensions and main accounts are created in the system, they are used on the **Configure account structures**, **Advanced rule structures**, and **Financial dimension configuration for integrating applications** pages.</span></span> <span data-ttu-id="ea03b-107">Ordningen som har angetts på dessa sidor används i systemet för dataregistrering och förbrukning.</span><span class="sxs-lookup"><span data-stu-id="ea03b-107">The order that is defined on those pages is used in the system for data entry and consumption.</span></span> <span data-ttu-id="ea03b-108">På vissa ställen i systemet visas ekonomiska dimensioner och huvudkonton i separata fält.</span><span class="sxs-lookup"><span data-stu-id="ea03b-108">In some places in the system, the financial dimensions and main accounts appear in separate fields.</span></span> <span data-ttu-id="ea03b-109">På andra ställen som t.ex. journaler visas ekonomiska dimensioner och huvudkonton som en enda sträng.</span><span class="sxs-lookup"><span data-stu-id="ea03b-109">In other places, such as journals, the financial dimensions and main accounts appear as a single string.</span></span>

## <a name="best-practices-for-setting-up-financial-dimensions-and-main-accounts-in-a-right-to-left-system"></a><span data-ttu-id="ea03b-110">Regelverk för att ställa in ekonomiska dimensioner och rubrikkonton i ett system från höger till vänster</span><span class="sxs-lookup"><span data-stu-id="ea03b-110">Best practices for setting up financial dimensions and main accounts in a right-to-left system</span></span>

- <span data-ttu-id="ea03b-111">När du väljer en av de dubbla avgränsarna väljer du ett av alternativen för dubbla avgränsare: dubbla bindestreck (`--`), dubbelstreck (`||`) eller dubbla punkter (`..`), eller dubbla understreck (`\\`).</span><span class="sxs-lookup"><span data-stu-id="ea03b-111">When you select the delimiter for charts of accounts, select one of the double delimiter options: double hyphen (`--`), double bar (`||`), double period (`..`), or double underscore (`\\`).</span></span>
- <span data-ttu-id="ea03b-112">När du skapar värden för ekonomisk dimension och huvudkonto använder du siffror och språktecken som skrivs från höger till vänster.</span><span class="sxs-lookup"><span data-stu-id="ea03b-112">When you create financial dimension and main account values, use only numbers and right-to-left language characters.</span></span>
- <span data-ttu-id="ea03b-113">Undvik att använda den valda kontoplanavgränsaren i värden frö ekonomisk dimension och huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="ea03b-113">Avoid using the selected chart of accounts delimiter in financial dimension and main account values.</span></span>

<span data-ttu-id="ea03b-114">Genom att följa regelverk, kan du garantera en konsekvent representation av den användardefinierade ordern i hela systemet.</span><span class="sxs-lookup"><span data-stu-id="ea03b-114">By following these best practices, you help guarantee consistent representation of the user defined-order throughout the system.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]