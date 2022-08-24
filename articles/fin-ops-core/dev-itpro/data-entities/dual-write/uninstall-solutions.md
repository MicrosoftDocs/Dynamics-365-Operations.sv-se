---
title: Avinstallera lösningar för dubbelriktad skrivning för programorkestrering
description: I denna artikel beskrivs hur du avinstallerar lösningar för dubbelriktad skrivning för programorkestrering.
author: RamaKrishnamoorthy
ms.date: 03/16/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2022-01-21
ms.openlocfilehash: fd9dc98ec1323a2ef262a330a400a6bd3833e554
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288743"
---
# <a name="uninstall-dual-write-application-orchestration-solutions"></a>Avinstallera lösningar för dubbelriktad skrivning för programorkestrering

[!include [banner](../../includes/banner.md)]

I denna artikel beskrivs hur du avinstallerar lösningar för dubbelriktad skrivning för programorkestrering.

Vissa kunder installerar oavsiktligt det installationspaket för dubbelriktad skrivning för programorkestrering som installerar flera lösningar i Microsoft Dataverse-miljön. Installation av överflödiga lösningar i paketet kan leda till oväntade och oönskade problem.

Om du vill åtgärda problem som är relaterade till installationen av paketet för dubbelriktad skrivning för programorkestrering avinstallerar du oönskade lösningar för dubbelriktad skrivning i följande ordning:

1. Dynamics365FinanceAndOperationsAnchor_managed
1. msdyn_OneFSSCM_managed (om detta finns)
1. Dynamics365FinanceAndOperationsDualWriteEntityMaps_managed
1. Dynamics365Notes_managed (För att avinstallera den här lösningen måste du registrera ett supportärende hos Microsoft.)
1. DualWriteCore_managed
1. Dynamics365AssetManagementApp_managed
1. Dynamics365AssetManagement_managed
1. Dynamics365SupplyChainExtended_managed
1. Dynamics365FinanceExtended_managed
1. HCMCommon_managed
1. Dynamics365FinanceAndOperationsCommon_managed
1. Dynamics365Company_managed
1. CurrencyExchangeRates_managed
1. msdyn_AssetCommon_managed
1. FieldServiceCommon_managed

Om part- och globala adressbokslösningar har installerats avinstallerar du lösningarna i följande ordning:

1. Dynamics365FinanceAndOperationsAnchor
1. Dynamics365FinanceAndOperationsDualWriteEntityMaps
1. msdyn_DualWriteCore
1. Dynamics365AssetManagementApp
1. Dynamics365AssetManagement
1. Dynamics365SupplyChainExtended
1. Dynamics365FinanceExtended
1. HCMCommon
1. Dynamics365FinanceAndOperationsCommon
1. Part
1. Dynamics365Company_managed
1. CurrencyExchangeRates
1. msdyn_AssetCommon
1. FieldServiceCommon
