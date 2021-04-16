---
title: Felsöka uppgradering och migrering till avancerad distributionslagerhantering
description: I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du uppgraderar och migrerar till avancerad lagerhantering.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 953b828667a01157767c3ca79349fe972b0fbe9b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826405"
---
# <a name="troubleshoot-upgrade-and-migration-to-advanced-warehouse-management"></a>Felsöka uppgradering och migrering till avancerad distributionslagerhantering

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du uppgraderar och migrerar till avancerad lagerhantering.

## <a name="i-receive-the-following-error-message-javasecuritycertcertpathvalidatorexception-trust-anchor-for-certification-path-is-not-found"></a>Följande felmeddelande visas: "java.security.cert.certPathValidatorException: Förtroendeankare för certifieringsväg hittades inte".

### <a name="issue-description"></a>Problembeskrivning

Det här felmeddelandet visas i mobilappen för distributionslagerhantering eftersom självsignerade certifikat inte är betrodda i Android 8+ i lokala miljöer.

### <a name="issue-resolution"></a>Problemlösning

Använd en extern (offentlig) certifikatutfärdare (CA). En korrigeringsfil för det här problemet finns tillgänglig i version 1.9.0.0 av distributionslagerappen. Mer information om det här problemet och hur du åtgärdar det finns i [felsökning av anslutningsproblem för mobilappen för distributionslagerhantering](troubleshoot-warehouse-app-connection.md).

## <a name="what-is-the-approved-process-for-moving-from-basic-warehousing-to-advanced-warehousing"></a>Vad är den godkända processen att flytta från grundläggande lagerstyrning till avancerad lagerstyrning?

### <a name="issue-description"></a>Problembeskrivning

Du kör för närvarande under lager/lagerhantering och använder grundläggande lagerfunktion och du vill flytta till avancerad lager för att dra nytta av mobila enheter, påfyllnader och arbete. Du får emellertid problem när du försöker att göra denna flyttning. Du kan till exempel inte ändra produkter så att de använder lagringsdimensioner (webbplats, lagerställe och plats), eftersom produkterna har transaktioner gentemot dem. Därför måste du lära den godkända processen att flytta från grundläggande lagerstyrning till avancerad lagerstyrning.

### <a name="issue-resolution"></a>Problemlösning

Mer information om processen för att flytta från grundläggande lagerstyrning till avancerad lagring finns i följande blogginlägg och dokumentation:

- [Aktivera lagerhanteringsprocessen för befintliga artiklar och lager](https://cleverax.wordpress.com/2017/12/06/d365fo-enable-warehouse-management-process-for-existing-items-and-warehouses/)
- [Migrering av Microsoft Dynamics AX WMS till nya R3 lagerställe- och transportfunktion](https://cloudblogs.microsoft.com/dynamics365/no-audience/2015/08/17/migration-of-microsoft-dynamics-ax-wms-to-new-r3-warehouse-and-transportation-functionality/)
- [WMSI/WMS2 artikelmigrering](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/05/03/wmsiwms2-item-migration/)
- [Uppgradera lagerstyrning från Microsoft Dynamics AX 2012 till Supply Chain Management](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/upgrade-migration-warehouse-management-processes)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]