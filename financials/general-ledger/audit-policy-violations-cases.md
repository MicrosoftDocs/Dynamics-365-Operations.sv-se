---
title: "Överträdelser av granskningspolicyn"
description: "Det här avsnittet innehåller en beskrivning av hur revisionsfall genereras från regelbrott för granskningspolicyregler. Här finns även information om hur olika granskningspolicyer använder datumintervallet för dokumenturval."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13091
ms.assetid: e0e66c6d-c396-4a9d-b3b6-3641d130fdc0
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: fbc8dd8f14bd6607081f7c479830c142a912339a
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="audit-policy-violations-and-cases"></a>Överträdelser av granskningspolicyn

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller en beskrivning av hur revisionsfall genereras från regelbrott för granskningspolicyregler. Här finns även information om hur olika granskningspolicyer använder datumintervallet för dokumenturval.

<a name="how-audit-cases-are-generated"></a>Hur revisionsärenden genereras
-----------------------------

Granskningspolicyn används för att identifiera utgiftsrapporter, inköpsorder och leverantörsfakturor som inte överensstämmer med affärsreglerna som du definierar och konfigurerar som granskningsregler. 

Granskningspolicyn körs i batchläget. När du kör en granskningspolicy, körs alla reglerna i policyn samtidigt.

Varje policyregel bedömer en uppsättning dokument. Policyregeln väljer dokument som finns i datumperioden och som matchar kriteriet som ställts in. Exempelvis kan en policyregel välja utgiftsrapporter med måltider som överstiger 500,00. En annan policyregel kan välja leverantörsfakturor som ska betalas till en viss leverantör. För varje dokument som väljs i uppsättningen, genereras en överträdelse. Överträdelsen är en post där ett visst dokument, som faktura 12345, inte följer policyregeln. 

Flera granskningsöverträdelseposter grupperas tillsammans och kopplas till revisionsfall. Som standard grupperas fall för varje granskningspolicy efter granskningsregel. Om du vill kan du välja andra grupperingsvillkor på sidan **Villkor för ärendegruppering**. Exempelvis kan du gruppera sidhuvud för utgifter efter projekt-ID och leverantörsfakturor efter leverantörskonto. I detta fall kommer alla överträdelser av utgiftsrubriker med samma projekt-ID att grupperas i samma ärende, och samtliga leverantörsfakturor som har samma leverantörskonto grupperas i samma ärende. 

> [!NOTE]
> För granskningsregler som baseras på frågetypen **Duplicera** grupperas inte överträdelser efter policyregel eller efter villkor som har angetts på sidan **Villkor för ärendegruppering**. I stället grupperas de efter de kriterier som är inbyggda i granskningsregeln. Om till exempel en policyregel utvärderar utgiftsrapporter för dubblettutgifter med samma belopp, handlar-id och datum, blir alla utgifter som har samma värden i dessa fält ett enda ärende. Alla utgifter som har andra värden, kommer att bli separata fall.

När revisionsfallen har skapats, hanteras de genom att använda de typiska processerna för ärendehantering.

## <a name="document-selection-date-ranges"></a>Datumintervall för dokumenturval
När en granskningspolicy körs, väljer varje policyregel dokument med den angivna typen som har ett datum som finns i datumintervallet för dokument. Datumintervallet anges på sidan **Ytterligare alternativ**. Många dokument har mer än ett kopplat datum. Datumfältet som granskningsregeln använder anges på sidan **Policyregeltyp**.

Nedan följer några andra sätt som en granskningspolicy använder datumintervallet på:

-   Policyn använder varje policyregelversion som gäller den sista dagen i dokumentdatumintervallet. Du kan visa giltighetsdatumet för varje policyregel på sidan **Granskningspolicyer**.
-   Policyn använder organisationsnoderna som är kopplade till policyn den sista dagen i datumintervallet. Endast organisationsnoderna som för närvarande är kopplade till policyn visas på listsidan **Granskningspolicyer**.
-   För policyregler som är baserade på frågetypen **Listsökning** utvärderar policyn dokument för övervakade enheter som gäller den sista dagen i dokumentdatumintervallet.


Mer information finns i [Regler för granskningspolicy](audit-policy-rules.md)




