---
title: Ställ in redovisningsbokföringsgrupper för moms
description: Moms beräknas och bokförs på huvudkontona som anges i redovisningsbokföringsgrupperna.
author: twheeloc
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxAccountGroup
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c353a4fbed3af0cd7477c9a1543baaf523da6f11
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735767"
---
# <a name="set-up-ledger-posting-groups-for-sales-tax"></a>Ställ in redovisningsbokföringsgrupper för moms

[!include [banner](../../includes/banner.md)]

Moms beräknas och bokförs på huvudkontona som anges i redovisningsbokföringsgrupperna. Redovisningbokföringsgrupper kopplas till varje momskod. Du kan ställa in enskilda redovisningsbokföringsgrupper för varje momskod, och du kan använda en redovisningsbokföringsgrupp för alla momskoder eller tilldela flera redovisningsbokföringsgrupper till momskoderna. I den här registreringen används demonstrationsföretaget DEMF. 

1. Gå till **Navigeringsfönster > Moduler > Moms > Inställningar > Moms > Redovisningsbokföringsgrupper**.
2. Klicka på **Ny**.
3. Skriv ett värde i fältet **Redovisningsbokföringsgrupp**.
4. I fältet **Beskrivning** anger du ett värde.
5. Välj huvudkontot för utgående moms som ska betalas till skattemyndigheten i fältet **Momsskuld**. Moms samlas in åt skattemyndigheten när du säljer momspliktiga varor och tjänster.  
6. Välj huvudkontot för inkommande moms som ska mottagas från skattemyndigheten i fältet **Momsfordran**. Leverantörer samlar in moms åt skattemyndigheten när du köper momspliktiga varor och tjänster. Det här fältet är inte tillgängligt om alternativet Använd momsbeskattningsregler har valts på sidan **Redovisningsparametrar**. Istället debiteras moms som betalats till leverantörer på samma konto som inköpen.   
7. I fältet **Importavgift, utgift**, välj huvudkontot för bokföring av avdragsgilla importavgifter som inte begärts eller rapporterats till skattemyndigheten av leverantörer i enlighet med reglerna för omvänd skattskyldighet i EU i fältet GST/HST. Alternativet **Importavgift** måste väljas för **Momskod** i **momsgruppen** som används i transaktionen. Det här fältet är inte tillgängligt om alternativet **Använd momsbeskattningsregler** har valts på sidan **Redovisningsparametrar** .   
8. Välj huvudkontot för bokföring av inkommande importmoms som ska betalas till skattemyndigheten i fältet **Importavgift, skuld**. Alternativet **Importavgift** måste väljas i **Momskod** i **Momsgrupp** för bokföring av **importavgiften**. Om alternativet **Använd momsbeskattningsregler** valts på sidan **Redovisningsparametrar** bokförs en motbokning på transaktionens utgiftskonto.   
9. Välj, i fältet **Kvittningskonto**, huvudkontot där nettosaldot för redovisningskontona som anges i fälten **Importavgift, skuld** och **Momsfordran** ska bokföras. Saldot skapas när momskvittningen och bokföringsjobbet har körts.  Om skattemyndigheten för kvittningsperioden är kopplad till ett leverantörskonto, bokförs saldot på leverantörskontot i stället.
10. Välj huvudkontot för att bokföra kassarabatten för momskoder som är kopplade till denna redovisningsbokföringsgrupp i fältet **Leverantörskassarabatt**. Det här är valfritt och om inget konto anges ska huvudkontot för **kassarabattkoder** användas. Det kan vara praktiskt att använda andra konton, per **redovisningsbokföringsgrupp**, om du använder alternativet för återföring av moms vid kassarabatter i momsgrupperna.  
11. Välj huvudkontot för att bokföra kassarabatten för **momskoder** som är kopplade till denna **redovisningsbokföringsgrupp** i fältet **Kundkassarabatt**. Det är valfritt och om inget konto anges, ska huvudkontot för **kassarabattkoder** användas. Det kan vara praktiskt att använda andra konton, per **redovisningsbokföringsgrupp**, om du använder alternativet för återföring av moms vid kassarabatter i **Momsgrupper**.  
12. Klicka på **Spara**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
