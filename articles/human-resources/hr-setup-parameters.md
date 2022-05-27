---
title: Konfigurera Personal-parametrar
description: Det här ämnet innehåller information om hur du ställer in företagsspecifika parametrar i Dynamics 365 Human Resources.
author: twheeloc
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1fc8ba3f69f216d66850485b6ba33cd324a57156
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689422"
---
# <a name="configure-human-resources-parameters"></a>Konfigurera Personal-parametrar

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Inställningarna för vissa Personalparametrar delas av alla företag, medan inställningarna för andra parametrar är företagsspecifika. Det här ämnet innehåller information om hur du ställer in personalparametrar.

Två sidor används för att ställa in personalparametrar. För parametrar som delas mellan företag, kan du använda de **mänskliga resurserna delas parametrar sidan** . För parametrar som är företagsspecifika (med andra ord inställningar tillämpas på ett enda företag) kan du använda den **mänskliga resursen parametrar sidan** .

![Gå till personalparametrar.](./media/hr-employee-self-service-human-resources-parameters.png)

På **mänskliga resurser parametrar sidan** , inställningarna är uppdelade i sex flikar:

- **Allmänt**
- **Rekrytering** (denna flik ingår inte i Dynamics 365 Human Resources)
- **Kompensation**
- **Nummerserier**
- **FMLA**
- **Självbetjäning för medarbetare**
- **Självbetjäning för chef**
- **Hantering av förmåner**
- **Tjänstledighet och frånvaro**
- **Betalningsmetoder**

Varje flik innehåller information som hänför sig till ett enda bolag.

## <a name="general"></a>Allmänt

Inställningar på **fliken Allmänt** definierar utseendet av information om frånvaro, skador och sjukdomar, och nyanställningar. Inställningarna på den här fliken definierar också några poster som visas såsom dig arbete. På den här fliken kan du:

- Välj en färg som ska användas för öppna frånvarotransaktioner.
- Ange formatmallen som ska användas för rapporter.
- Aktivera integrering mellan utbildningskurser och frånvaroregistrering.
- Välj den frånvarokod som används för att kontrollera den här integrationen.
- Ange hur länge du ska behålla incidenter för skada och sjukdom.
- Ange standard-ID som ska visas när en ny medarbetare anställs.
- Ange datumet som används för att beräkna tjänsteår. 

![Fliken Allmänt.](./media/hr-setup-parameters-general.png)

## <a name="recruitment"></a>Rekrytering

Inställningarna på fliken **Rekrytering** definierar de dokumenttyper som används för korrespondens automatiskt till sökande. Du kan även ange vilket rekryteringsprojekt som används för oombedda ansökningar.

Den period som anges i **Åldersfördelning för rekryteringsprojekt** avgör vilka rekryteringsprojekt som inkluderas i panelen **Åldersfördelningsprojekt** i arbetsytan **Rekryteringshantering**. Den period som definieras för deadlinevarning för ansöka används för att visa rekryteringsprojekt som närmar sig sista ansökningsdag på panelen **Sista ansökningsdag närmar sig** i arbetsytan **Rekrytering**.

Mer information om rekrytering finns i [Rekrytera jobbsökande](hr-personnel-recruit.md).

## <a name="compensation"></a>Kompensation

I Dynamics 365 Finance anger inställningarna på fliken **Kompensation** om användare måste bekräfta att de vill spara information för en fast eller variabel kompensationsplan. Om du markerar **Aktivera spara validering** kommer användarna när de stänger en relaterad kompensationsplanssida att få ett meddelande som frågar om de vill spara posten. Vissa sidor i kompensationshantering låter inte användare ta bort information. Genom att meddela användarna att bekräfta att de vill spara information, du kan begränsa den mängd information som sparas men inte tas bort senare. Om du rensar **Aktivera spara validering** sparas poster alltid omedelbart, möjligen innan användaren är redo. Om du använder performance management, **fliken ersättningar** kan du också välja ett betyg modell att använda i stället för den modell som är tilldelade till ersättningsplaner när prestanda är klassad.

I Personal kan du använda fliken **Kompensation** om du vill välja att begränsa åtkomsten till kompensationsplaner och att ange en standardvaluta.

Mer information om att kompensationsplaner finns i [Översikt över kompensationsplaner](hr-compensation-overview.md).

![Fliken Kompensation.](./media/hr-setup-parameters-compensation.png)

## <a name="number-sequences"></a>Nummerserier

Inställningarna på fliken **Nummerserie** bestämmer vilka sekvenser som används för att automatiskt tilldela ID till artiklar i Personal, till exempel:

- Ansökningar
- Frånvaroregistreringar
- Resultat för kompensationsprocessen
- Ärendenummer
- Kurser
- Kursagendor

För att bibehålla nummersekvensreferenser och koder, använd listsidan **Nummersekvenser** (klicka på **Organisationsadministration > Nummersekvenser > Nummersekvenser**).

Mer information finns i [Nummerserier (översikt)](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

> [!NOTE]
> Det antal timmar som arbetas inte överstiga 1250 och längden på anställningen får inte överskrida 12 månader. Dessa största värden i enlighet med federal lag i USA.

![Fliken Nummerserie.](./media/hr-setup-parameters-number-sequences.png)

## <a name="fmla"></a>FMLA

På fliken FMLA ställer du in kraven på FMLA-berättigande och FMLA-berättigandetimmar. Mer information finns i [Konfigurera parametrar för tjänstledighet och frånvaro](hr-leave-and-absence-parameters.md).

![Fliken FMLA.](./media/hr-setup-parameters-fmla.png)

## <a name="employee-self-service"></a>Självbetjäning för medarbetare

Inställningarna på fliken **Självbetjäning för medarbetare** påverkar hur **Självbetjäning för medarbetare** visas för medarbetarna. På denna flik kan du utföra följande uppgifter:

- Ange ett namn för arbetsytan **Självbetjäning för medarbetare**
- Välja vilken information en chef kan ange för medarbetare
- Lägga till användbara länkar för medarbetare
- Hindra medarbetare från att lägga till eller redigera affärskontaktinformation. Mer information finns i [Begränsa redigering av personlig information](hr-employee-self-service-restrict-editing.md).

Mer information om hur du konfigurerar **Självbetjäning för medarbetare** finns i [Självbetjäningsöversikt för medarbetare och chefer](hr-employee-manager-self-service-overview.md).

![Fliken Självbetjäning för medarbetare.](./media/hr-setup-parameters-employee-self-service.png)

## <a name="manager-self-service"></a>Självbetjäning för chef

Inställningarna på fliken **Självbetjäning för chef** påverkar det som cheferna ser i **Självbetjäning för chef**. På den här fliken kan du konfigurera följande alternativ:

- Intervallet för utgående poster
- Informationschefer kan visa i utgångsposter
- Information om huruvida chefer kan visa öppna befattningar för utökade rapporter
- Vyer av medarbetare
- Användbara länkar för chefer

Mer information om hur du konfigurerar **Självbetjäning för chef** finns i [Självbetjäningsöversikt för medarbetare och chefer](hr-employee-manager-self-service-overview.md).

![Fliken Självbetjäning för chef.](./media/hr-setup-parameters-manager-self-service.png)

## <a name="benefits-management"></a>Hantering av förmåner

På fliken **Förmånshantering** kan du konfigurera e-postalternativ för förmånshantering. Mer information om hur du konfigurerar och använder förmånshanteringar finns i [Översikt över förmånshantering](hr-benefits-management-overview.md).

![Fliken Hantering av förmåner.](./media/hr-setup-parameters-benefits-management.png)

## <a name="leave-and-absence"></a>Tjänstledighet och frånvaro

Läs mer om ställa in och använda ledighet och frånvaro i [Översikt av tjänstledighet och frånvaro](hr-leave-and-absence-overview.md).

## <a name="payment-methods"></a>Betalningsmetoder

På fliken **Betalningsmetoder** kan du välja de betalningsmetoder som stöds av din organisation. Mer information om att konfigurera kompensationsplaner finns i [Översikt över kompensationsplaner](hr-compensation-overview.md).

![Fliken Betalningsmetoder.](./media/hr-setup-parameters-payment-methods.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
