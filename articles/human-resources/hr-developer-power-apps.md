---
title: Utöka Talent med Power Apps och Power Automate
description: Den här artikeln beskriver några exempel på tilläggsscenarier för Microsoft Dynamics 365 Human Resources som använder Microsoft Power Apps och Microsoft Power Automate.
author: negudava
manager: Annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: Dynamics 365 Human Resources;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core;Experience Apps;Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 36b8145764338b91bfedf96c43a7137a89831742
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410114"
---
# <a name="extend-with-power-apps-and-power-automate"></a><span data-ttu-id="cc450-103">Utöka med Power Apps och Power Automate</span><span class="sxs-lookup"><span data-stu-id="cc450-103">Extend with Power Apps and Power Automate</span></span>

<span data-ttu-id="cc450-104">Den här artikeln beskriver några exempel på tilläggsscenarier för Microsoft Dynamics 365 Human Resources som använder Microsoft Power Apps och Microsoft Power Automate.</span><span class="sxs-lookup"><span data-stu-id="cc450-104">This article describes some examples of extensibility scenarios for Microsoft Dynamics 365 Human Resources that use Microsoft Power Apps and Microsoft Power Automate.</span></span> <span data-ttu-id="cc450-105">Du kan importera lösningspaketet som associeras med varje exempel i din Power Apps-miljö.</span><span class="sxs-lookup"><span data-stu-id="cc450-105">You can import the solution package that is associated with each example into your Power Apps environment.</span></span> <span data-ttu-id="cc450-106">Du kan sedan använda paketen antingen som vägledning eller som utgångspunkt för att implementera scenarier som gäller för din organisation.</span><span class="sxs-lookup"><span data-stu-id="cc450-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc450-107">Om du vill använda de mallar och program som beskrivs i det här avsnittet ”i befintligt skick” bör du testa dem och se till att de täcker alla de scenarier som avser implementeringen.</span><span class="sxs-lookup"><span data-stu-id="cc450-107">If you want to use the templates and apps that are described in this topic "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cc450-108">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="cc450-108">Prerequisites</span></span>

- <span data-ttu-id="cc450-109">Om du vill importera paket måste användarna ha behörighet **Environment Maker**.</span><span class="sxs-lookup"><span data-stu-id="cc450-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="cc450-110">Användare måste ha en Power Apps Plan 2-licens eller en Power Apps Plan 2 utvärderingslicens för att exportera eller importera appar.</span><span class="sxs-lookup"><span data-stu-id="cc450-110">To export or import apps, users must have a Power Apps Plan 2 license or a Power Apps Plan 2 trial license.</span></span>

## <a name="integration-with-office-365-power-automate"></a><span data-ttu-id="cc450-111">Integration med Office 365, Power Automate</span><span class="sxs-lookup"><span data-stu-id="cc450-111">Integration with Office 365, Power Automate</span></span>

<span data-ttu-id="cc450-112">Appen **Integrering med Office 365** kan användas för att hämta teaminformation för inloggade användare från Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="cc450-112">The **Integration with Office 365** app can be used to extract team information for signed-in users from Microsoft Office 365.</span></span> <span data-ttu-id="cc450-113">Den refererar medarbetare i personal för att extrahera identifieringstyper för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="cc450-113">It references workers in Human Resources to extract employee identification types.</span></span> <span data-ttu-id="cc450-114">Chefer kan kontrollera utgångsdatum för medarbetar-ID-typer.</span><span class="sxs-lookup"><span data-stu-id="cc450-114">Managers can check expiration dates of employee ID types.</span></span> <span data-ttu-id="cc450-115">De kan också skicka en e-postpåminnelse om medarbetar-ID-typen förfaller.</span><span class="sxs-lookup"><span data-stu-id="cc450-115">They can also send an email reminder if the employee ID type is expiring.</span></span> <span data-ttu-id="cc450-116">Power Automate kan integreras med Power Apps för att skicka påminnelsen.</span><span class="sxs-lookup"><span data-stu-id="cc450-116">Power Automate integrates with Power Apps to send this reminder.</span></span> <span data-ttu-id="cc450-117">Bekräftelse kommer att skickas tillbaka till Power Apps från Power Automate när påminnelsen skickas.</span><span class="sxs-lookup"><span data-stu-id="cc450-117">Confirmation will be sent back to Power Apps from Power Automate when the reminder is sent.</span></span> <span data-ttu-id="cc450-118">Identifieringstyper inkluderar körkort, pass och andra godtagbara former av ID.</span><span class="sxs-lookup"><span data-stu-id="cc450-118">Identification types include driver's license, passport, and other acceptable forms of ID.</span></span>

<span data-ttu-id="cc450-119">Du kan utöka den här appen för andra scenarier.</span><span class="sxs-lookup"><span data-stu-id="cc450-119">You can extend this app for other scenarios.</span></span> <span data-ttu-id="cc450-120">Exempelvis användas den för att visa semesterinformation för team, kalenderhändelser och alla teamspecifika händelser.</span><span class="sxs-lookup"><span data-stu-id="cc450-120">For example, you can use it to show team vacation information, calendar events, and any team-specific events.</span></span>

<span data-ttu-id="cc450-121">För att hämta mallen **Integration med Office 365, Power Automate**-appen, gå till [Integration med Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) på Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="cc450-121">To download the **Integration with Office 365, Power Automate** app, go to [Integration with Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) on the Microsoft Download Center.</span></span>

## <a name="power-automate--sql-connect-and-execute"></a><span data-ttu-id="cc450-122">Power Automate – anslut och kör SQL</span><span class="sxs-lookup"><span data-stu-id="cc450-122">Power Automate – SQL Connect and execute</span></span>

<span data-ttu-id="cc450-123">Mallen **Power Automate – anslut och kör SQL** ansluter till Microsoft SQL Server och gör att SQL-frågor kan köras.</span><span class="sxs-lookup"><span data-stu-id="cc450-123">The **Power Automate – SQL Connect and execute** template connects to Microsoft SQL Server and enables SQL queries to be run.</span></span>

<span data-ttu-id="cc450-124">Även om den här mallen läser och uppdaterar SQL-register kan du utöka den och använda den för andra scenarier.</span><span class="sxs-lookup"><span data-stu-id="cc450-124">Although this template reads and updates SQL tables, you can extend it and use it for other scenarios.</span></span> <span data-ttu-id="cc450-125">Den kan exempelvis användas för att fylla på ett mellanlagringsregister i Common Data Service med poster från SQL Server och regelbundet synkronisera mellanlagringsregister med hjälp av en stegvis distribution från SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cc450-125">For example, you can use it to fill a staging table in Common Data Service with records from SQL Server, and to periodically synchronize the staging table by using an incremental push from SQL Server.</span></span>

<span data-ttu-id="cc450-126">Den avancerade frågan är integrerad med flödet för att aktivera datatransformation och stegvis distribution.</span><span class="sxs-lookup"><span data-stu-id="cc450-126">Advanced Query is integrated with Flow to enable Data transformation and incremental push.</span></span>

<span data-ttu-id="cc450-127">För att hämta mallen **Power Automate – ansluta och köra SQL** gå till [Power Automate – ansluta och köra SQL](https://go.microsoft.com/fwlink/?linkid=2081789) på Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="cc450-127">To download the **Power Automate – SQL Connect and execute** template, go to [Power Automate – SQL Connect and execute](https://go.microsoft.com/fwlink/?linkid=2081789) on the Microsoft Download Center.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cc450-128">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="cc450-128">Additional resources</span></span>

[<span data-ttu-id="cc450-129">Appen Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="cc450-129">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>