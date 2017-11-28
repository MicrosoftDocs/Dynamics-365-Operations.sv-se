--- 
title: "Ställ in redovisningsbokföringsgrupper för moms"
description: "Moms beräknas och bokförs på huvudkontona som anges i redovisningsbokföringsgrupperna."
author: twheeloc
manager: AnnBe
ms.date: 10/26/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ef3cad6538d9efbd1c1881f4b7d771382d9b1ba8
ms.openlocfilehash: e50fc2b6b8f4cd91e9a5593297fff2e9a6ef5525
ms.contentlocale: sv-se
ms.lasthandoff: 10/26/2017

---
# <a name="set-up-ledger-posting-groups-for-sales-tax"></a>Ställ in redovisningsbokföringsgrupper för moms

[!include[task guide banner](../../includes/task-guide-banner.md)]

Moms beräknas och bokförs på huvudkontona som anges i redovisningsbokföringsgrupperna. Redovisningbokföringsgrupper kopplas till varje momskod. Du kan ställa in enskilda redovisningsbokföringsgrupper för varje momskod, och du kan använda en redovisningsbokföringsgrupp för alla momskoder eller tilldela flera redovisningsbokföringsgrupper till momskoderna. I den här registreringen används demonstrationsföretaget DEMF. 

1. Gå till Skatt > Inställningar > Moms > Redovisningsbokföringsgrupper.
2. Klicka på Ny.
3. Skriv ett värde i fältet Redovisningsbokföringsgrupp.
4. Ange ett värde i fältet Beskrivning.
5. Välj huvudkontot för utgående moms som ska betalas till skattemyndigheten i fältet Momsskuld.
    * Moms samlas in åt skattemyndigheten när du säljer momspliktiga varor och tjänster.  
6. Välj huvudkontot för inkommande moms som ska mottagas från skattemyndigheten i fältet Momsfordran.
    * Leverantörer samlar in moms åt skattemyndigheten när du köper momspliktiga varor och tjänster. Det här fältet är inte tillgängligt om alternativet Använd momsbeskattningsregler har valts på sidan med redovisningsparametrar. Istället debiteras moms som betalats till leverantörer på samma konto som inköpen.   
7. Välj huvudkontot för bokföring av avdragsgilla importavgifter som inte begärts eller rapporterats till skattemyndigheten av leverantörer i enlighet med reglerna för omvänd skattskyldighet i EU i fältet GST/HST.
    * Alternativet Importavgift måste markeras för momskoden i momsgruppen som används i transaktionen.  Det här fältet är inte tillgängligt om alternativet Använd momsbeskattningsregler har valts på sidan med redovisningsparametrar.   
8. Välj huvudkontot för bokföring av inkommande importmoms som ska betalas till skattemyndigheten i fältet Importavgift, skuld.
    * Alternativet Importavgift måste markeras i momskoden i momsgruppen för bokföring av importavgiften. Om alternativet Använd momsbeskattningsregler markerats i redovisningsparametrarna bokförs en motbokning på transaktionens utgiftskonto.   
9. Välj huvudkontot där nettosaldot för redovisningskontona som anges i fälten Importavgift, skuld och Momsfordran ska bokföras i fältet Kvittningskonto.
    * Saldot skapas när momskvittningen och bokföringsjobbet körs.  Om skattemyndigheten för kvittningsperioden är kopplad till ett leverantörskonto, bokförs saldot på leverantörskontot i stället.   
10. Välj huvudkontot för att bokföra kassarabatten för momskoder som är kopplade till denna redovisningsbokföringsgrupp i leverantörkassarabattfältet.
    * Det är valfritt och om inget konto anges, ska huvudkontot för kassarabattkoder användas. Det kan vara praktiskt att använda andra konton, per redovisningsbokföringsgrupp, om du använder alterantivet för återföring av moms vid kassarabatter i momsgrupperna.  
11. Välj huvudkontot för att bokföra kassarabatten för momskoder som är kopplade till denna redovisningsbokföringsgrupp i kundkassarabattfältet.
    * Det är valfritt och om inget konto anges, ska huvudkontot för kassarabattkoder användas. Det kan vara praktiskt att använda andra konton, per redovisningsbokföringsgrupp, om du använder alterantivet för återföring av moms vid kassarabatter i momsgrupperna.  
12. Klicka på Spara.


