---
title: Ställ in flexkreditprogram
description: Du kan använda flexkreditprogram i Microsoft Dynamics 365 Human Resources för att registrera anställda i förmåner enligt ett förutbestämt antal flexsaldon.
author: twheeloc
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitCreditPrograms, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ff3bd2c4d39a4411b5a5cb82e4281ff4af98ff0d
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337065"
---
# <a name="set-up-flex-credit-programs"></a>Ställ in flexkreditprogram

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Du kan använda flexkreditprogram i Microsoft Dynamics 365 Human Resources för att registrera anställda i förmåner enligt ett förutbestämt antal flexsaldon. Medarbetarna kan välja hur de vill fördela sina flexkredit. Om t.ex. en medarbetare täcks av sin makes sjukförsäkringsplan kan de vilja använda de krediter de annars skulle ha använt för hälsoskydd mot andra förmåner. 

1. I arbetsytan **Hantering av förmåner** under **Planer**, välj **Flexkreditprogram**.

2. Välj **Ny**.

3. Ange värden för de följande fälten:

   | Fält | Beskrivning |
   | --- | --- |
   | **ID för förmånens kredit** | Det unika ID:t för flexkreditprogrammet. |
   | **Beskrivning** | En beskrivning av flexkreditprogrammet. | 
   | **Från-datum** | Det datum då flexkreditprogrammet blir aktivt. |
   | **Till-datum** | Slutdatumet för flexkreditprogrammet. Du kan lämna standardvärdet (12/31/2154) för att ange att flexkreditprogrammet inte har ett förfallet förfallodatum. |
   | **Totalt kreditvärde** | Det antal tillgodohavanden som varje medarbetare måste använda för sina förmåner. |
   | **Regel för proportionell fördelning** | Den regel som ska användas för att allokera flexkrediter när en medarbetare anställs i mitten av den flexkreditperioden. </br></br><ul><li>**Ingen** – medarbetaren får inga flexkrediter om de anställs efter att flexprogramperioden har inletts.</li><li>**Fullständig kredit** – medarbetaren får hela beloppet för flexsaldon, oavsett när de anställs.</li><li>**Proportionell fördelning** – medarbetaren får ett proportionellt antal flexsaldon baserat på startdatumet.</li></ul> |
   | **Formel för proportionell fördelning av flexkredit** | Den regel som ska användas för att allokera flexkrediter för medarbetare som anställs i mitten av flexkreditperiodens förmånsperiod. Proportionell fördelning baseras på anställningens startdatum. Detta fält används endast om du väljer **Proportionell fördelning** i fältet **Regel för proportionell fördelning**. </br></br><ul><li>**Dagligen** – Proportionell fördelning av antalet flexsaldon som en medarbetare får på dagnivå. Det totala antalet flexsaldon divideras med antalet dagar i perioden. Om till exempel din förmånsperiod är 400 dagar delas det totala antalet flexsaldon med 400 för att beräkna antalet flexsaldon för medarbetare som får inlevereras per dag.</li><li>**Aktuell månad** – Proportionell fördelning av antalet flexsaldon som en medarbetare får från månadsnivån, avrundad till aktuell månad. Det totala antalet flexsaldon divideras med antalet månader i perioden. Om till exempel din förmånsperiod är 15 månader delas det totala antalet flexsaldon med 15 för att beräkna antalet flexsaldon för medarbetare som får inlevereras per månad.</li><li>**Följande månad** – Proportionell fördelning av antalet flexsaldon som en medarbetare får från månadsnivån, avrundad till nästa månad. Det totala antalet flexsaldon divideras med antalet månader i perioden. Om till exempel din förmånsperiod är 15 månader delas det totala antalet flexsaldon med 15 för att beräkna antalet flexsaldon för medarbetare som får inlevereras per månad.</li></ul> |
   


[!INCLUDE[footer-include](../includes/footer-banner.md)]
