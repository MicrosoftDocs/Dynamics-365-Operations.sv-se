---
title: Avinstallera lösningar för dubbelriktad skrivning för programorkestrering
description: I detta ämne beskrivs hur du avinstallerar lösningar för dubbelriktad skrivning för programorkestrering.
author: RamaKrishnamoorthy
ms.date: 03/16/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2022-01-21
ms.openlocfilehash: 781b2cb19a563d5712fa65718c93bfdc242f0c4a
ms.sourcegitcommit: abfaef124c8747827d6f297821f01f1f6fbca6b7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/17/2022
ms.locfileid: "8455329"
---
# <a name="uninstall-dual-write-application-orchestration-solutions"></a>Avinstallera lösningar för dubbelriktad skrivning för programorkestrering

[!include [banner](../../includes/banner.md)]

I detta ämne beskrivs hur du avinstallerar lösningar för dubbelriktad skrivning för programorkestrering.

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
