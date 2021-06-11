---
title: Hantera ändringar i formler och deras ingredienser
description: I det här avsnittet beskrivs hur du hanterar recepthantering och hanterar ändringar av huvuddata för processtillverkning.
author: t-benebo
ms.date: 05/19/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-05-19
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 825cc5b9355695a648c857e5197b5b93a21fdb43
ms.sourcegitcommit: 588f8343aaa654309d2ff735fd437dba6acd9d46
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2021
ms.locfileid: "6115221"
---
# <a name="manage-changes-in-formulas-and-their-ingredients"></a>Hantera ändringar i formler och deras ingredienser

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Om du använder processtillverkningsfunktionerna för Microsoft Dynamics 365 Supply Chain Management, du kan också använda relaterade formelhanteringsfunktioner för att hantera följande ändringar:

- **Formel och planera artiklar:** Hantera ändringar av ingredienser i formler och deras samprodukter och biprodukter.
- **Samprodukter och biprodukter:** Redigera kvantiteter och annan information om samprodukterna och biprodukterna i en formel.
- **Faktisk/nominell vikt:** Hantera ändringar av faktisk/nominell vikt.

## <a name="turn-on-this-feature-in-your-system"></a>Aktivera funktionen i systemet

Om du vill använda denna funktion måste du utföra följande uppgifter:

1. Aktivera *konstruktionsändringshantering*-funktionen och dess konfigurationsnyckel som beskrivs i [Översikt över konstruktionsändringshantering](product-engineering-overview.md). Som nämns i det ämnet, se till att du också aktiverar licensnyckeln **Ändringshantering för processtillverkning** som finns kapslad under huvudlicensnyckeln **Teknikändringshantering**.
1. Aktivera funktionen *Hantera ändringar av formler och deras ingredienser* i [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="feature-naming-conventions"></a>Namnkonventioner för funktioner

I användargränssnittet för Supply Chain Management (UI) och dokumentationen kallas ändringshanteringsfunktionen ofta för *konstruktionsändringshantering*, och de hanterbara produkterna kallas vanligtvis för *konstruktionsprodukter*. Även om den här terminologin inte vanligtvis associeras med hanteringen av formler för processtillverkning, bör du tänka på att inom teknik, ändra hanteringen som helt enkelt ändra hanteringen, och du bör tänka på att tekniska produkter är versionerade produkter.

## <a name="work-with-formula-change-management-features"></a>Arbeta med funktioner för formeländringshantering

I följande lista sammanfattas hur funktionerna för att hantera förändringar gäller för formelhantering. Det innehåller även länkar till mer information. Eftersom formeländringshantering använder funktionerna för konstruktionsändringshantering bör du lära dig hur konstruktionsändringshantering fungerar i allmänhet så att du kan använda den för att hantera dina formler och deras ingredienser.

- **Centraliserad produktdatahantering** – Ställ in en organisation som, via en hanterad frisläppningsprocess, säkerställer att korrekta och relevanta produktdata blir tillgängliga för användarna i hela företaget. Mer information finns i [regler för konstruktionsföretag och dataägarskap](engineering-org-data-ownership-rules.md).
- **Produktversion** - Spåra ändringar av produkter via produktversioner och kontrollera produkten genom alla faser i leveranskedjan. På det här sättet kan du spåra de ändringar som du har gjort. För mer information, se [Konstruktionsversioner och kategorier av konstruktionsprodukter](engineering-versions-product-category.md).
- **Livscykelhantering för produkt** – Hantera synligheten för produktdata i hela organisationen, och kontrollera tillgängligheten för produktversioner i varje steg i leveranskedjan. Du har detaljerad kontroll över när en produktversion kan användas i specifika affärsprocesser, och du kan skapa egna livscykeltillstånd som passar verksamhetens behov. Mer information finns i [produktens livscykeltillstånd och transaktioner](product-lifecycle-state-transactions.md).
- **Formeländringshantering** – Användarna i hela organisationen kan begära ändringar av formler. Använd ändringsorder för att bedöma och dokumentera effekten av föreslagna ändringar. Lägg till arbetsflöden för att hantera ändringsprocessen och frisläppa nya versioner av produkten och dess formel. För mer information, se [Hantera ändringar av konstruktionsprodukter](engineering-change-management.md).
- **Beredskapskontroll** – Använd systemkontroller och användarvägledning (enkäter och checklistor) för att säkerställa att alla produktdata är fullständigt angivna innan produkten frisläpps. Mer information finns i [Produktberedskap](product-readiness.md).
- **Förbättrad produktlanseringsfunktion** – Frisläpp fullständigt definierade versioner av en produkt och dess formel från en organisation (juridisk person) till andra juridiska personer. Du kan till och med bestämma om produktinformationen måste granskas eller redigeras före frisläppning. Mer information finns i [Frisläppa produktstruktur](release-product-structure.md).

Observera att de flesta avsnitt som är länkade till i föregående lista ger exempel som baseras på strukturlistor. Formler fungerar dock på liknande sätt. Här är några ytterligare koncept som är användbara när du använder ändringshantering (eller bara receptändringshantering) för att hantera formler och strukturlistor:

- För varje [kategori för produktdesign](engineering-versions-product-category.md) kan du ange produktionstypen (strukturlista, recept eller planeringsartikel). Du kan även ange om support för faktisk/nominell vikt krävs för produkter där denna kategori används.
- Samprodukter och biprodukter är inte tekniska produkter. Därför är de inte versionerade. Om du måste ändra dem behöver du bara skapa en ny produkt. Det här gör underhållet enklare.
- Du kan hantera slutartiklar som är strukturlistor och som har underordnade formelartiklar. Funktionen fungerar för alla kombinationer av strukturlistor som innehåller formler och/eller formler som innehåller strukturlistor.
