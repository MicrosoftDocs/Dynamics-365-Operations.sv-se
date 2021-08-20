---
title: Formler och formelversioner
description: Det här avsnittet innehåller information om formler och formelversioner. En formel definierar material, komponenter och resultat för en viss process i processtillverkning. Formler används för att planera och framställa produkter i processtillverkning.
author: cvocph
ms.date: 09/12/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PlanActivity, ReqSupplyDemandSchedule, EcoResProductProdTypeFormulaNoActiveFormulaFormPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d86b0c8fa3c6379b9f1df11fd6b20f9e263656c2b98ea00f4225aebd5d25ac41
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6780062"
---
# <a name="formulas-and-formula-versions"></a>Formler och formelversioner

[!include [banner](../includes/banner.md)]

En formel definierar material, komponenter och resultat för en viss process i processtillverkning. Tillsammans med motsvarande väg definierar formeln hela processen inom processtillverkning. Formler används för att planera och framställa produkter i processtillverkning.

En formel består av de ingredienser och kvantiteter som krävs för att producera en viss kvantitet av en receptvara. Beroende på vilken uppgift som du utför har du åtkomst till formelfunktionen via lagerstyrningen eller produktinformationshanteringen.

## <a name="formulas-and-formula-lines"></a>Formler och formelrader
En formel består av en eller flera formelrader som identifierar de ingredienser eller artiklar som ingår i formeln. En formelrad kan innehålla artiklar till en strukturlista, formelartiklar, artiklar för faktisk/nominell vikt, inköpta artiklar, delprodukter och biprodukter. Eftersom många används i flera produkter kan en vara användas i flera formler.

Ett exempel på en formel är formeln för en chocolate chip-kaka. Ingredienserna till formeln använder flera rader, till exempel mjöl, socker, ägg, smör och chokladbitar. Formeln för chocolate chip-cookies innehåller komponenter som troligen används i andra formler. När du gör chocolate chip cookies kanske det blir rester över, till exempel smulor, eller också kan vissa cookies gräddas för länge eller för kort. Dessa artiklar kan fungera som samprodukter eller biprodukter beroende på produktionsåtgärderna.

När du skapar en formelrad använder du radtypen för att ange hur systemet ska hantera raden när du kör huvudplaneringen och framställer batchorder. Olika radtyper ger olika resultat. I följande tabell beskrivs de radtyper som du kan markera. 

| Radtyp     | beskrivning  |
|---------------|--------------|
| Artikel          | Välj **Vara** när varan är råmaterial eller ett halvfabrikat som plockas från lagret eller när varan är en tjänst. |
| Fiktiv       | Välj **Fiktiv** när du vill bryta ned formelartiklar på lägre nivåer som finns på formelrader. När du uppskattar batchordern och formelartiklarna bryts, visas komponentartiklarna som formelrader i batchordern. Dessutom läggs motsvarande flöden till i produktionsflödet. Formelartiklar bryts ned genom att använda den aktuella konfigurationen. När du använder radtypen **Fiktiv** kan du hantera produktions och måttkonfigurationer som sker på olika formelnivåer. Om du väljer **Fiktiv** för en produkt på snabbfliken **Tekniker** på sidan **Frisläppt produktinformation** och sedan använder den här produkten i en formel, ändras radtypen för formelraden ändras till **Fiktiv**. Du kan inte välja **Fiktiv** för en faktisk/nominell vikt eller för artiklar vars produktionstyp är **Samprodukt**, **Biprodukt** eller **Planeringsvara**. |
| Peggad leverans | Välj **Peggad leverans** för att skapa batchorder, tillverkningsorder, kanban, överföringsorder eller inköpsorder för den komponent som finns på receptraden. Tillhörande order skapas baserat på standardinställningarna för order samt ingrediensernas produktionstyp, och skapas när du beräknar batch-ordern. De begärda ingredienskvantiteterna reserveras för batchordern. |
| Leverantör        | Markera **Leverantör** om tillverkningsprocessen använder en underleverantör och du vill skapa en underproduktions- eller inköpsorder för underleverantören. Den tjänst eller det arbete som underleverantören utför måste skapas genom att använda en formelvara eller en tjänstevara. Du kan koppla varan till den överordnade varan som en formelrad. Flödet måste innehålla en operation som är tilldelad underleverantörens verksamhetsresurs. Denna åtgärd kopplas till formelraden via **Åtg.nr.** . |

## <a name="formula-versions"></a>Formelversioner
När du skapar en ny formel måste du först skapa en formelversion innan du lägger till artiklar och dessas specifika egenskaper i formelraden. Alla formler måste ha minst en version. Knappen **Godkänd** på en formelversion blir tillgänglig först efter det att en versionspost har sparats. Varje formelversionspost kopplas till en eller flera samprodukter och biprodukter som kan tillverkas när du tillverkar den färdiga produkten. Många produkter kan framställas av samma ingredienser i olika batch-storlekar, i multipler eller genom att använda olika kapaciteter. Du kan skapa så många formelversioner som du behöver.

Använd gällande datumintervall eller antalsfältet ”Från” för att hantera flera aktiva formelversioner. Flera aktiva formelversioner kan endast finnas om datumspannet och kvantiteten ”från” inte överlappar varandra.

Till skillnad från strukturlistor, där en strukturlista ofta associeras med flera strukturlisteversioner, förekommer normalt endast en formelversion per formel. Kom ihåg att endast en formelversion kan aktiveras för disponeringsdimension och kvantitet för en viss produkt. Det kan emellertid finnas många receptversioner av andra skäl, och du kan markera dessa manuellt när du skapar en batchorder.

## <a name="approve-and-activate-formulas-and-formula-versions"></a>Godkänn och aktivera formler och formelversioner
Formler och formelversioner måste godkännas innan de kan användas för planering och produktion. Formler är vanligtvis aktiverade innan de används. I samband med produktion kan du emellertid välja en formelversion som har godkänts men som inte är aktiverad.

Du kan ange parametrarna **Blockera redigering** och **Blockera borttagande av godkännande** på sidan **Produktionskontrollparametrar** för att säkra en formel eller en formelversion.

Om du väljer **Blockera redigering** och formeln godkänns, kan inga fält i formelraderna tas bort eller redigeras. Om du tar bort godkännandet av receptet du emellertid ta bort och ändra formelraderna. Du kan också skapa nya formler och nya formelversioner.

Om du väljer **Blockera borttagande av godkännande** kan du inte ta bort godkännandet av en godkänd formel eller formelversion. Du kan emellertid skapa nya formler och nya formelversioner, och du kan ta bort aktiveringen av formelversionen.

Du kan lägga till flera nivåer av kontroll med hjälp av funktionen för elektronisk signatur. När en användare har ställts in så att en elektronisk signatur krävs vid tidpunkten för formelgodkännande, visas en **Signatur**-sida när formeln är aktiverad. Användaren måste vara auktoriserad att signera elektroniskt, och intyget måste valideras innan ändringen kan bekräftas. Om signaturen inte kan verifieras nekas godkännandet eller borttagningen av godkännandet, och ändringen som initierade godkännandet eller borttagningen av godkännandet återgår till sitt ursprungliga tillstånd.

## <a name="use-the-scalable-feature"></a>Använd funktionen Skalbar
Funktionen Skalbar finns bara om samtliga formelns varukomponenter har angetts som **Variabel förbrukning**. Funktionen är inte tillgänglig om varukomponenterna är angivna som **Fast förbrukning** eller **Stegförbrukning**. Om du ändrar en ingrediens i en formel när den skalbara funktionen är i bruk, kommer kvantiteten för de andra ingredienserna som du väljer att justeras. Storleken på receptet justeras också. På samma sätt kommer kvantiteten av samtliga skalbara ingredienser att ändras om du ändrar formelstorleken. Den här funktionen är avsedd specifikt för formelskapande och underhåll. Den anger inte om mängden av en ingrediens skalas uppåt eller nedåt i en batch.

## <a name="use-step-consumption"></a>Använd stegförbrukning
Stegförbrukning eliminerar kravet att ange en kvantitet för en ingrediens på fliken **Formelrad**. Stegförbrukning har istället konfigurerats att ha ett **Från serie**-värde och ett **Kvantitet**-värde. Informationen från den Stegförbrukning per serie-post som uppfyller kvantiteten i batch-ordern väljs. Stegförbrukningen är användbar när förbrukningstakten inte är linjär med avseende på batchorderns storlek, och ökar behovet endast när en viss kvantitetströskel uppnås. Du aktiverar funktionen för en ny formel i gruppen **Förbrukningsberäkning** och ändra formelinställningen för tillämpbar ingrediens från **Standard** till **Steg**. Du anger denna förbrukningsmetod på fliken **Inställningar** på sidan **Formelrad**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]