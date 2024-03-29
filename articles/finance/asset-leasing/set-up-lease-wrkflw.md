---
title: Konfigurera arbetsflöden för leasinggodkännande
description: I det här ämnet beskrivs hur du konfigurerar ett godkännandearbetsflöde som ska köras när en ny leasing skapas.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0162e559f8aaec248cfb9042b0152788536c9fc9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870290"
---
# <a name="set-up-lease-approval-workflows"></a>Konfigurera arbetsflöden för leasinggodkännande

[!include [banner](../includes/banner.md)]

I det här ämnet beskrivs hur du konfigurerar ett godkännandearbetsflöde som ska köras när en ny leasing skapas. Mer information om hur du använder arbetsflödet finns i [Använda arbetsflöden för leasinggodkännande](use-create-lease-wrkflw.md). 

1. Gå till **Leasing av tillgångar \> Konfigurera \> Leasingarbetsflöde**.
2. Välj **Nytt** på sidan **Leasingarbetsflöde**.
3. I dialogrutan som visas, **Arbetsflödestyp**, väljer du länken **Leasingarbetsflöde**.

    Programmet öppnas. När det har körts, logga in på Azure Active Directory (Azure AD) för att omdirigeras till arbetsflödesprogrammet.

4. Dra elementet **Arbetsflödesgodkännande av leasing** till arbetsflödet.
5. Anslut en nod från **Start** till **Arbetsflödesgodkännande av leasing**. Anslut sedan **Arbetsflödesgodkännande av leasing** till **Slut**.
6. Dubbelklicka på **Arbetsflödesgodkännande av leasing**.
7. Välj **Egenskaper** och ange ett namn på arbetsflödet under **Grundinställningar**.

    På den här sidan kan du också konfigurera fler parametrar för arbetsflödet. Om du har aktiverat **Automatiska åtgärder** kommer systemet automatiskt att vidta en särskild åtgärd. Meddelanden kan skickas om de har angetts på fliken **Meddelanden**. På fliken **Avancerade inställningar** kan du ange en slutlig godkännare, ange en tidsgräns och ange specifika åtgärder som måste utföras.

8. Välj **Stäng** när du är klar med att ange arbetsflödesparametrarna.
9. Välj **Steg 1** och sedan **Egenskaper**.
10. Under **Grundinställningar** anger du ett namn på steget, skapar en ämnesrad för godkännandet och anger sedan instruktioner för godkännandet.
11. Välj en tilldelningstyp på sidan **Tilldelning**.
12. Om du vill tilldela specifika användare till godkännandet väljer du **Användare**, väljer de användare som godkänner leasingar och väljer sedan **Stäng**.
13. Välj **Spara och stäng** för att skapa arbetsflödet. Välj sedan **OK** när du uppmanas att göra det.
14. Välj **Stäng** på sidan **Skapa arbetsflöde**.
14. Välj det nya arbetsflödet och välj sedan **Versioner**. Välj sedan **Aktivera** för att säkerställa att arbetsflödet är aktivt.
15. Välj **Nära**. Den nya aktiva versionen visas.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
