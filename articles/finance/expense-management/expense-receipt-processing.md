---
title: Bearbetning av utgiftskvitto
description: Det här ämnet ger information om optisk teckenläsning (OCR) av kvitton. Den här funktionen är utformad för att förbättra användarupplevelsen när utgiftsrapporter skapas i Microsoft Dynamics 365 Finance.
author: stsporen
manager: AnnBe
ms.date: 11/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: stsporen
ms.search.validFrom: 2019-11-20
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: efba2faf9428d9b556d74273bc7daadba7211c48
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/08/2020
ms.locfileid: "3248973"
---
# <a name="expense-receipt-processing"></a>Bearbetning av utgiftskvitto

[!include [banner](../includes/banner.md)]

Utgiftsregistrering har förbättrats genom introduktion av OCR (optisk teckenläsning) för kvitton. Den här funktionen är utformad för att förbättra användarupplevelsen när utgiftsrapporter skapas.

## <a name="key-features"></a>Nyckelfunktioner

- Handelsnamn, datum och totalbelopp hämtas från kvitton.
- Funktionen försöker matcha ej kopplade kvitton till ej kopplade utgiftstransaktioner.
- Användare kan skapa manuellt registrerade utgiftstransaktioner från kvitton.

## <a name="usage-examples"></a>Exempel på användning

- **Koppla automatiskt kvitton som inkluderar kreditkortstransaktioner när en utgiftsrapport skapas.**

    1. Öppna arbetsytan **utgiftshantering**.
    2. På fliken **kvitton** kontrollerar du att det inte finns några kopplade kvitton. Du kan även överföra kvitton på fliken **kvitton**.
    3. På fliken **utgifter** kontrollerar du att det inte finns några kopplade utgifter. Vanligtvis importerar utgiftsadministratören dessa utgifter från kreditkortsutfärdaren.
    4. Välj **Ny utgiftsrapport**. Observera att du kan inkludera utgifter och kvitton även när du skapar en utgiftsrapport. Om du lägger till både utgifter och kvitton utlöses automatisk matchning av kvitton mot utgifterna.

- **Skapa en utgift eller matcha en utgift från ett kvitto.**

    1. På en utgiftsrapport på fliken **kvitton** bifogar du ett kvitto genom att välja **Lägg kvitton**.
    2. Lägg märke till under den uppladdade bilden av kvittot, observera alternativet **Skapa** och **Matcha**.

        - Välj **skapa** om du vill skapa en manuellt angiven utgiftstransaktion och fyll i de värden som hämtas från kvittot.
        - Om du väljer **matcha** kommer systemet att försöka matcha en befintlig utgift mot kvittot.

## <a name="installation"></a>Installation

Den här funktionen fungerar tillsammans med **Utgiftsrapporter på nytt sätt**, så att utgiftsupplevelsen blir enklare att använda.

Om du vill använda de avancerade utgiftsfunktionerna installerar du tillägget utgiftshanteringstjänst för Microsoft Dynamics 365 Finance och aktiverar funktionerna i din instans. Du kan komma åt tillägget från ditt projekt i Microsoft Dynamics Lifecycle Services (LCS).

1. Logga in på LCS och öppna den önskade miljön.
2. Gå till **Fullständiga detaljer**.
3. Välj **underhåll** eller rulla ned till snabbfliken **miljötillägg**.
4. Välj **installera ett nytt tillägg**.
5. Välj **utgiftshanteringstjänst**.
6. Följ installationsguiden och godkänn villkoren.
7. Välj **Installera**.

I arbetsytan **utgiftshantering** aktiverar du följande funktioner:

- Utgiftsrapporter på nytt sätt
- Matcha automatiskt och skapa utgift från kvitto

När du aktiverar dessa funktioner utförs följande åtgärder:

- Den befintliga arbetsytan för **utgiftshantering** ersätts med den nya arbetsytan.
- Ett nytt menyalternativ för utgiftsfältets synlighet läggs till.
- Du kan fortfarande öppna den tidigare sidan **utgiftsrapporter** genom att gå till **utgiftshantering > mina utgifter > utgiftsrapporter**.
- Arbetsflöden och eventuella godkännanden leder fortfarande till sidan för befintliga utgiftsrapporter.
- Kvitton kommer att bearbetas via Microsoft Azure Cognitive Services och metadata extraheras och läggs till.
- Ett alternativ läggs till som gör att du kan skapa en utgiftsrapport som innehåller matchade ej kopplade kvitton.
- Ett alternativ som läggs till i utgiftsrapporter gör att du kan skapa en utgiftsrad från ett kvitto eller ett försök att matcha en befintlig inleverans till en befintlig utgiftsrad.

Mer information om hur utgiftsrapporter är förväntat finns i [Utgiftsrapporter på nytt sätt](ExpenseWorkspaceNew.md).

## <a name="frequently-asked-questions"></a>Vanliga frågor

**Används mina data för modellerna i Microsoft?**

Nej, Microsoft har skapat en allmän modell för maskininlärning för den mottagande bearbetningstjänsten. Den här modellen är inte baserad på kvitton som du har överfört.

**Var är den här funktionen tillgänglig och bearbetad?**

USA stöds för närvarande.

**Var hamnar mina kvitton?**

Finance kommer att kontakta Cognitive Services för att extrahera fältdata. Cognitive Services behåller en kopia av ditt kvitto i upp till 24 timmar under bearbetningen. När bearbetningen är klar kommer Cognitive Services att ta bort kvittot. Kvitton lagras fortfarande i Finance.

Mer information finns i [aktivera kvittoförståelse med formulärtolkens nya förmåga](https://azure.microsoft.com/blog/enable-receipt-understanding-with-form-recognizer-s-new-capability/).
