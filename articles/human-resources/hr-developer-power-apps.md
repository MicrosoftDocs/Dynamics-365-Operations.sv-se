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
ms.openlocfilehash: 8d4185b958ed35e9d2bc764db8ea77b3a2f53c37
ms.sourcegitcommit: 13c4a6f98ccce243d6befde90992aefcf562bdab
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029875"
---
# <a name="extend-with-power-apps-and-power-automate"></a>Utöka med Power Apps och Power Automate

Den här artikeln beskriver några exempel på tilläggsscenarier för Microsoft Dynamics 365 Human Resources som använder Microsoft Power Apps och Microsoft Power Automate. Du kan importera lösningspaketet som associeras med varje exempel i din Power Apps-miljö. Du kan sedan använda paketen antingen som vägledning eller som utgångspunkt för att implementera scenarier som gäller för din organisation.

> [!IMPORTANT]
> Om du vill använda de mallar och program som beskrivs i det här avsnittet ”i befintligt skick” bör du testa dem och se till att de täcker alla de scenarier som avser implementeringen.

## <a name="prerequisites"></a>Förutsättningar

- Om du vill importera paket måste användarna ha behörighet **Environment Maker**.
- Användare måste ha en Power Apps Plan 2-licens eller en Power Apps Plan 2 utvärderingslicens för att exportera eller importera appar.

## <a name="integration-with-office-365-power-automate"></a>Integration med Office 365, Power Automate

Appen **Integrering med Office 365** kan användas för att hämta teaminformation för inloggade användare från Microsoft Office 365. Den refererar medarbetare i personal för att extrahera identifieringstyper för medarbetare. Chefer kan kontrollera utgångsdatum för medarbetar-ID-typer. De kan också skicka en e-postpåminnelse om medarbetar-ID-typen förfaller. Power Automate kan integreras med Power Apps för att skicka påminnelsen. Bekräftelse kommer att skickas tillbaka till Power Apps från Power Automate när påminnelsen skickas. Identifieringstyper inkluderar körkort, pass och andra godtagbara former av ID.

Du kan utöka den här appen för andra scenarier. Exempelvis användas den för att visa semesterinformation för team, kalenderhändelser och alla teamspecifika händelser.

För att hämta mallen **Integration med Office 365, Power Automate**-appen, gå till [Integration med Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) på Microsoft Download Center.

## <a name="power-automate--sql-connect-and-execute"></a>Power Automate – anslut och kör SQL

Mallen **Power Automate – anslut och kör SQL** ansluter till Microsoft SQL Server och gör att SQL-frågor kan köras.

Även om den här mallen läser och uppdaterar SQL-register kan du utöka den och använda den för andra scenarier. Den kan exempelvis användas för att fylla på ett mellanlagringsregister i Common Data Service med poster från SQL Server och regelbundet synkronisera mellanlagringsregister med hjälp av en stegvis distribution från SQL Server.

Den avancerade frågan är integrerad med flödet för att aktivera datatransformation och stegvis distribution.

För att hämta mallen **Power Automate – ansluta och köra SQL** gå till [Power Automate – ansluta och köra SQL](https://go.microsoft.com/fwlink/?linkid=2081789) på Microsoft Download Center.

## <a name="additional-resources"></a>Ytterligare resurser

[Appen Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>
[Migrera mellan innehavare och program](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
