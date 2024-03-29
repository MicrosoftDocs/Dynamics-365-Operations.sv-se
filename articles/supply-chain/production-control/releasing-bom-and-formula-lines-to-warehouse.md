---
title: Frisläpp strukturliste- och formelrader till lagerstället
description: Denna artikel beskriver processen för att frisläppa råmaterial för strukturlisterader och formelrader till lagret.
author: johanhoffmann
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm, ProdParmReleaseToWarehouse, WHSReleaseToWarehouseProdBOM
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 53e3a943dbd6cf982101f42ed8f94b7e0f46597c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860621"
---
# <a name="release-bom-and-formula-lines-to-the-warehouse"></a>Frisläpp strukturliste- och formelrader till lagerstället

[!include [banner](../includes/banner.md)]

Denna artikel beskriver processen för att frisläppa råmaterial för strukturlisterader och formelrader till lagret. När du frisläpper en strukturlista eller formelrad till lagret fastställer systemet först om material redan finns på platsen för produktionsinleverans i fabriken där materialet ska förbrukas i produktionsprocessen.

- Om materialet är tillgängligt på platsen för produktionsinleverans hämtas det från den platsen omedelbart efter att signal ges för frisläppning av material till lagret.
- Om materialet är inte tillgänglig på platsen för produktionsinleverans indikerar materialfrisläppningen att materialet måste flyttas från platserna i lagerstället till platsen för produktionsinleverans. Materialet flyttas via lagerställearbete för plockning av råmaterial. Därför måste lagerprocesser för råmaterialplockning vara konfigurerad. Mer information finns i [Översikt över lagerpåfyllnad](../warehousing/replenishment.md) och [Kontrollera lagerarbetet genom arbetsmallar och platsdirektiv](../warehousing/control-warehouse-location-directives.md).

## <a name="methods-for-releasing-bom-and-formula-lines"></a>Metoder för att frisläppa strukturlista och formelrader

Du kan konfigurera frisläppningen av strukturlistan och formelrader så att den sker som en del av frisläppningen av en produktionsorder eller batchorder. Alternativt kan frisläppningen kontrolleras av ett batchjobb eller utföras som en manuell åtgärd.

Den metod som används för att frisläppa strukturlista och formelrader styrs av parametern **Frisläppning av produktionsrad**. Du hittar den här parametern på **produktionskontroll**\>**inställningar**\>**produktionsparametrar**.

- **Frisläpp strukturliste- och formelrader som en del av frisläppningen av produktion eller batchorder** – med den här metoden frisläpps strukturlista och formelrader för en produktions- eller batchorder som en del av processen med att frisläppa ordern. Vanligtvis under frisläppning av produktions- eller batchorder kommer produktionsjobb att frisläppas till verkstadsarbetare och produktionspapper skrivs ut. Under denna process kommer status för ordern att ändras till **frisläppt**.
- **Frisläpp strukturliste- och formelrader via ett batchjobb eller som en manuell åtgärd** – med den här metoden kan strukturlista och formelrader endast frisläppas genom batchjobbet **automatisk version av strukturliste- och formelrader** eller som en manuell åtgärd. För att manuellt frisläppa strukturliste- och formelrader på sidan för produktionorderlista eller produktionsorderinformationssidan i åtgärdsfönstret, väljer du **Frisläpp till lagerställe**.

För en snabb demonstration av hur du frisläpper strukturlistor och formlrader till produktion genom att använda ett batchjobb kan du titta på den här korta YouTube video: [Släpp produktionsplockning till lagret i batch](https://www.youtube.com/watch?v=8urAJn50dQ8).

## <a name="releasing-the-bom-and-formula-lines-by-using-a-batch-job"></a>Att frisläppa strukturliste- och formelrader med hjälp av ett batchjobb

Batchjobbet **Automatisk frisläppning av strukturliste- och formelrader** går genom valda strukturliste- och formelrader som har en resterande kvantitet att frisläppa. Jobbet tar bara hänsyn till order som har statusen **frisläppt**, **startad**, eller **rapporterat som färdig**. Om strukturliste- eller formelraden har en resterande kvantitet att släppa frisläppa, frisläpper jobbet upp till den kvantitet som kan täckas av den kvantitet som redan har reserverats fysiskt och kvantiteten är fysiskt tillgänglig.

### <a name="example-of-a-batch-job-release"></a>Exempel på en frisläppning av batchjobb

| Scenario | Återstående kvantitet att frisläppa | Fysisk reserverad kvantitet | Fysisk tillgänglig kvantitet | Kvantitet som frisläppts av batchjobbet |
|----------|-------------------------------|------------------------------|-------------------------------|------------------------------------|
| 1        | 100                           | 20                           | 90                            | 100                                |
| 2        | 100                           | 20                           | 70                            | 90                                 |
| 3        | 100                           | 0                            | 90                            | 90                                 |
| 4        | 100                           | 0                            | 110                           | 100                                |
| 5        | 100                           | 20                           | 0                             | 20                                 |

### <a name="batch-job-setup"></a>Inställning av batchjobb

I fråga om batchjobbet **Automatisk frisläppning av strukturliste- och formelrader** kan du skapa ett filtervillkor för att ange hur många dagar i förväg som jobbet ska söka efter rader som har ej frisläppta kvantiteter. I frågan för jobbet, i fältet **Råmaterialdatum** kan du använda funktionen **(LessThanDate())** som ett filtervillkor.

Följande bild visar en produktionsorder som har två jobb, 10 och 20, som täcker sammansättning och förpackning av tillverkningsordern. Varje jobb konfigureras till att använda en mängd material. I den här bilden är tidsgränsen för frisläppningen som anges av den gröna pilen nedanför tidslinjen lika med antalet dagar som har angetts i villkoret **(LessThanDate())**. Till exempel **(LessThanDate(2))** anger att jobbet ska söka efter ej frisläppta kvantiteter endast inom tidsgräns på två dagar.

![Exempel på en produktions med två batchjobb.](media/bach-job-setup.PNG)

## <a name="releasing-material-per-operation-number-or-in-proportion-to-the-amount-of-finished-goods"></a>Frsiläppa material per åtgärdsnummer eller i förhållande till mängden färdiga varor

Om du frisläpper material med hjälp av parameterinställningen **Vid frisläppning av produktionsorder**, när du gör en manuell frisläppning har du två alternativ för att styra materialfrisläppningen:

- Frisläpp material per åtgärdsnummer.
- Frisläpp material i förhållande till mängden färdiga varor.

### <a name="release-material-per-operation-number"></a>Frisläpp material per åtgärdsnummer

För att kontrollera de åtgärder som materialet ska frisläppas till, används sidan **Frisläpp till lagerställe**.

- Välj **produktionskontroll**\>**tillverkningsorder**\>**alla produktionsorder**, välj en produktionsorder och klicka sedan på fliken **lagerställe**, välj **frisläpp till lagerställe**. Använd sedan **Från oper.nr.** och fälten **Till oper.nr.** för att ange intervallet av åtgärdsnummer.

Följande bild visar en produktionsorder som använder två åtgärder 10 och 20. I det här exemplet begränsar du frisläppning till åtgärd 10, endast material M9203 kommer att frisläppas.

![Exempel på frisläppning av material per åtgärdsnummer.](media/two-operations.PNG)

Titta på den här korta YouTube-videon för en snabb demonstration av hur du frisläpper material i förhållande till mängden färdiga varor: [Förbättringar av tillverkningsorderns leveransprocess](https://www.youtube.com/watch?v=Rm3ojAz6Zu0).

### <a name="release-material-in-proportion-to-the-amount-of-finished-goods"></a>Frisläpp material i förhållande till mängden färdiga varor.

Du kan frisläppa råmaterial för en delkvantitet av färdiga varor, eller i en viss enhet.

- Du kan frisläppa råmaterial för en delkvantitet av färdiga varor, eller i en viss enhet genom att välja **produktionskontroll**\>**tillverkningsorder**\>**alla produktionsorder**, välj en produktionsorder och klicka sedan på fliken **lagerställe**, välj **frisläpp till lagerställe**. Ange sedan en kvantitet i fältet **Kvantitet**.

    Till exempel en tillverkningsorder skapas och planeras för 1 000 stycken (st). Produktionslagerarbetsledaren planerar produktionen av 100 st. för nästa skift och vill frisläppa material endast för det skiftet. I det här fallet kan arbetsledaren använda fältet **kvantitet** för att frisläppa material för 100 st. som har planerats för nästa skift.

- Du kan frisläppa råmaterial i en specifik enhet genom att välja **produktionskontroll**\>**tillverkningsorder**\>**alla produktionsorder**, välj en produktionsorder och klicka sedan på fliken **lagerställe**, välj **frisläpp till lagerställe**. Använd fältet **Enhet** för att välja enhet av den färdiga varan att frisläppa material i.

    Enheter som är tillgängliga fastställs i enhetssekvensgrupp-ID för den färdiga varan.

    Till exempel har en färdig vara följande enhetskonvertering mellan kilo (kg) och lastpall (PL): 1 PL = 100 kg. Skapa en tillverkningsorder för 10 000 kg. av färdiga varor kan du frisläppa råmaterial för antalet lastpallar som du planerar att producera. Välj **PL** som enhet, och välj sedan ett motsvarande värde i fältet **kvantitet**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]