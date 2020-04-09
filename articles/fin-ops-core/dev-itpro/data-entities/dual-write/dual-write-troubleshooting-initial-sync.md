---
title: Felsöka problem under första synkroniseringen
description: Det här avsnittet innehåller felsökningsinformation som kan hjälpa dig att åtgärda problem som kan uppstå under initial synkronisering.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: d51b547093825a6e7730b5fdfcfb1c081776c63c
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172724"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a>Felsöka problem under första synkroniseringen

[!include [banner](../../includes/banner.md)]



Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Common Data Service. Det ger särskilt information som kan hjälpa dig att åtgärda problem som kan uppstå under initial synkronisering. 

> [!IMPORTANT]
> Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen. I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a>Sök efter inledande synkroniseringsfel i en Finance and Operations-app

När du har aktiverat mappningsmallen ska status för mappningarna **köras**. Om status **inte körs** har fel uppstått vid den ursprungliga synkroniseringen. Om du vill visa felen väljer du fliken **Information om initial synkronisering** på sidan **Dubbelriktad skrivning**.

![Fliken Information om initial synkronisering](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a>Det går inte att slutföra den första synkroniseringen: 400 Felaktig begäran

**Den roll som krävs för att åtgärda problemet:** systemadministratör

Följande felmeddelande kan visas när du försöker köra mappningen och den första synkroniseringen:

*Fjärrservern returnerade ett fel: (400) felaktig begäran.) AX, exporten upptäckte ett fel*

Här följer ett exempel på det fullständiga felmeddelandet.

```console
Dual write Initial Sync completed with status: Error. Following are the details:
Executed leg: From AX Financial dimensions to CRM msdyn_dimensionattributes
with exported records count: 0, ImportRecordsErrorCount: 0,
ImportRecordsInsertedCount: 0 and ImportRecordsUpdatedCount: 0
ErrorsDetails:
Dual write Initial sync failed
Message: ([Bad Request], The remote server returned an error: (400) Bad Request.), AX export encountered an error
Stacktrace: at
Microsoft.Dynamics.Integrator.QueryGenerator.AxClient.\<ExportAxPackage\>d__16.MoveNext()
in X:\\bt\\1024532\\repo\\src\\Core\\QueryGenerator\\AxClient.cs:line 265
\--- End of stack trace from previous location where exception was thrown ---
at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
at Microsoft.D365.ServicePlatform.Context.ServiceContext.Activity.\<ExecuteAsync\>d__11\`2.MoveNext()
\--- End of stack trace from previous location where exception was thrown ---
```

Om detta fel inträffar konsekvent och du inte kan slutföra den ursprungliga synkroniseringen följer du stegen nedan för att åtgärda problemet.

1. Logga in på den virtuella datorn (VM) för Finance and Operations-appen.
2. Öppna Microsoft Management Console. 
3. I fönstret **tjänster** ser du till att tjänsten ramverk för dataimport och export av Microsoft Dynamics 365 körs. Starta om den om den har stoppats eftersom den första synkroniseringen kräver det.

## <a name="initial-synchronization-error-403-forbidden"></a>Fel vid första synkronisering: 403 förbud

Följande felmeddelande kan visas under första synkroniseringen:

*(\[Förbjudet\], Fjärrservern returnerade ett fel: (403) Förbjudet.), AX-exporten upptäckte ett fel*

Gör så här om du vill åtgärda problemet.

1. Logga in på Finance and Operations-appen.
2. På sidan **Azure Active Directory-appar** ta bort klienten **DtAppID** och lägg sedan till den igen.

![Lista över Azure AD-appar](media/aad_applications.png)

## <a name="self-reference-failures-during-initial-synchronization"></a>Självrefererande fel vid inledande synkronisering

Ett felmeddelande av följande slag kan visas om någon av dina mappningar har självreferenser:

*På leverantör V2, visas följande fel: Post-ID: ny post, ErrorMessage: Det gick inte att matcha GUID för fältet: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. Uppslagsvärdet hittades inte: CN-001. Prova denna UR för att kontrollera om referensdata existerar: `https://sampleorg.crm.dynamics.com/api/data/v9.0/msdyn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber` t.ex. 'CN-001'*

Den här typen av fel inträffar under den första synkroniseringen av mappningar som innehåller självreferenser. I föregående exempel refererar fältet fakturakonto till leverantörsenheten.

Du kan åtgärda problemet genom att köra mappningen två gånger innan den inledande synkroniseringen lyckas.

