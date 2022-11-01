---
title: Installera tillägget för mikrotjänster i Lifecycle Services
description: I denna artikel beskrivs hur du installerar tillägget för e-fakturering i Microsoft Dynamics Lifecycle Services (LCS).
author: gionoder
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 938b00192acc0ff5534239f2f280792471181fad
ms.sourcegitcommit: 1ecfc1d8afb2201ab895ae6f93304ba2b120f14b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2022
ms.locfileid: "9710819"
---
# <a name="install-the-add-in-for-microservices-in-lifecycle-services"></a>Installera tillägget för mikrotjänster i Lifecycle Services

[!include [banner](../includes/banner.md)]

För autentisering i e-faktureringstjänsten måste du registrera din Microsoft Dynamics 365 Finance- eller Dynamics 365 Supply Chain Management-miljö i tjänsteplattformen genom att installera tillägget för din miljö i Microsoft Dynamics Lifecycle Services (LCS).

Följ dessa steg för att registrera en miljö.

1. Logga in på LCS-kontot.
2. Välj ett LCS-projekt på projektinstrumentpanelen.
2. I projektet på instrumentpanelen **Miljöer** väljer du din distribuerade miljö. Miljön du väljer måste köras.
3. Under fliken **Power Platform-integrering**, i avsnittet **Miljötillägg**, väljer du **Installera ett nytt tillägg**.
4. Välj **e-fakturering**.
5. I fält **AAD app-ID** ange det fasta värdet i **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Detta värde är fält. Se till att du bara anger en global unik identifierare (GUID). Du får inte ta med några andra symboler, till exempel blanksteg, kommatecken, punkter eller citationstecken.
6. I fältet **AAD innehavar-ID** anger du innehavar-ID för ditt Azure abonnemangskonto. Den Azure Active Directory (Azure AD)-klientorganisation som du anger ska vara densamma som används för RCS.
7. Granska villkoren och markera sedan kryssrutan.
8. Välj **Installera**. Efter några minuter bör statusen ändras från **installera** till **installerad**. Du kanske måste uppdatera sidan för att kunna se denna förändring.

e-fakturering är nu redo att användas.

> [!NOTE]
> Företag har vanligtvis flera miljöer inom Ekonomi- eller Supply Chain Management-miljöer. Dessa miljöer omfattar produktionsmiljöer, UAT-miljöer (User Acceptance Test) samt utvecklingsmiljöer (sandbox). Du måste slutföra föregående förfarande för samtliga miljöer som du vill ansluta till e-fakturering.
