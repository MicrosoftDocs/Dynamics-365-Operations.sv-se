---
title: Allokeringsvillkor
description: Det här ämnet ger information om hur du använder allokeringsvillkor på ett huvudkonto.
author: rachel-profitt
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount, AllocationTerms
audience: Application User
ms.reviewer: roschlom
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-06-15
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 957baba1364fbbd4a51c6f51b0fad5bf8db46680fa97b9d3d0474dc015064609
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6776538"
---
# <a name="allocation-terms"></a>Allokeringsvillkor

[!include [banner](../includes/banner.md)]

Det här ämnet ger information om hur du använder allokeringsvillkor på ett huvudkonto. Allokeringsvillkor används för att fördela belopp mellan flera redovisningskontokombinationer. De hjälper till att garantera att utgifter eller intäkter debiteras för rätt objekt i redovisningen.

Varje allokeringsvillkor som du skapar på ett huvudkonto definierar den procentandel av en verifikation som ska tilldelas från ett huvudkonto för en enda källa och en kombination av ekonomiska dimensioner. Dessutom definierar du huvudkontomål och ekonomiska dimensioner där beloppet ska fördelas. 

När du definierar den ekonomiska källdimensionen för allokeringen kan du välja om varje dimension är specifik eller inte specifik. Specifik anger att den ekonomiska dimensionen för källtransaktionen måste matcha den valda dimensionen. När du väljer icke-specifik anger det att ett värde för den ekonomiska dimensionen kan bidra till en matchning.

När du definierar målredovisningskontot för ett allokeringsvillkor måste du ange det huvudkonto som du allokerar beloppet till. Du kan använda samma huvudkonto där källtransaktionen bokförs till, eller ett annat huvudkonto. Om samma huvudkonto används visas en varning när posten sparas. Förutom att ange huvudkontot måste du även ange måldimensionerna. För varje dimension kan du ange om du vill behålla det ekonomiska värdet för käll dimensionen eller ändra det. Om du väljer Nej måste du välja ett nytt värde för den ekonomiska dimensionen. Om du väljer Ja anges ingen ytterligare information och systemet underhåller de ursprungliga ekonomiska dimensionerna när du bokför.

Det finns ingen begränsning för antalet allokeringar som du kan lägga till i ett huvudkonto. Summan av procenten som ska allokeras på en fördelningsperiod får dock inte överstiga 100. Du kan skapa allokeringar för mindre än 100 procent om en del av det ursprungliga verifikationsbeloppet ska finnas kvar i ekonomiska källdimensioner. Allokeringsvillkor kan läggas till i ett huvudkonto som en juridisk person åsidosätta. Om du använder en delad kontoplan måste tilldelningsvillkoren definieras för varje juridisk person. Om du vill komma åt knappen **allokeringsvillkor** måste du först markera kryssrutan **allokering** på åsidosättning av juridiska personen.

## <a name="allocation-term-example"></a>Exempel på allokeringsvillkor
Du har definierat ett kostnadsställe för organisationen som kallas för FÖRETAG, numrerat 000. När fakturor bokförs för förbrukningsutgifter kodas de till detta kostnadsställe för FÖRETAGET. Ditt företag har definierat en regel som alla förbrukningsutgifter ska fördelas med en procentsats för var och en av de enskilda kostnadsställena. Övriga ekonomiska dimensioner för avdelnings- och affärsenheter förblir oförändrade.

I det här exemplet skapas ett nytt allokeringsvillkor för huvudkontot för förbrukningsutgifter. En rad skapas för varje kostnadsställe med den procentsats som ska tilldelas. **Urvalskriterierna** för de ekonomiska källdimensionerna för varje rad är **specifika** för **kostnadsstället** och värdet anges till 000: FÖRETAG. För avdelning och affärsenhet är **urvalskriteriet** inte **specifikt**.

På snabbfliken **målredovisningskontot** är huvudkontot samma kostnadskonto för verktyg och **behåll ekonomiska källdimensioner** anges till **Ja** för **Affärsenhet** och **Avdelning.** **Behåll ekonomiska källdimensioner** anges till **Nej** för **Kostnadsställe** och det valda värdet kommer att vara varje kostnadsställe som du allokerar till. Om det finns tre kostnadsställen att tilldela till skapas tre allokeringsvillkor. Den enda skillnaden mellan varje allokeringsvillkor är det kostnadsställe som anges på målredovisningskontot.

## <a name="create-an-allocation-term-on-a-main-account"></a>Skapa ett allokeringsvillkor på ett huvudkonto

1. I **Navigeringsfönster** gå till > **Moduler > Redovisning > Kontoplan > Konton > Huvudkonton**.
2. Hitta och markera önskad post i listan.
3. På snabbfliken **Åsidosättningar för juridisk person** väljer du **Lägg till**.
4. Markera **Företaget** och välj sedan **Lägg till**.
5. Markera kryssrutan **Allokering**.
6. Välj **Allokeringsvillkor** .
7. Välj **Redigera** om du vill ändra standardposten eller välj **ny** om du vill lägga till en post.
8. I fältet **procent** anger du den procentandel av verifikationstransaktionerna som du vill fördela.
9. På snabbfliken **ekonomisk källdimension**, i **urvalskriterier** för varje ekonomisk dimension, väljer du ett alternativ.
    - Om du väljer **specifik** väljer du värdet för den ekonomiska dimensionen i listrutan till höger.
    - Om du väljer **ej specifik** krävs ingen ytterligare information för den ekonomiska dimensionen.
10. På snabbfliken **redovisningskonto** i fältet **Till konto** väljer du det huvudkonto där du vill fördela procent satsen för verifikationstransaktionen.
11. I **Behåll ekonomiska källdimensioner** för varje ekonomisk dimension väljer du ett alternativ.
    - Om du väljer **Nej** väljer du sedan värdet för den ekonomiska dimensionen i listrutan till höger där du vill att verifikationstransaktionen ska fördelas.
    - Om du väljer **Ja** krävs ingen ytterligare information. Systemet behåller värdet på den ursprungliga verifikationen när du bokför allokeringen.
12. Upprepa steg 7-11 för varje ytterligare allokering. Summan av alla allokeringar visas i fältet **total procentsats**. Beloppet får inte överstiga 100.
13. Stäng alla sidor.

>[!NOTE] 
> Du kan också använda knappen **Kopiera** för att duplicera den valda allokeringen.

När ett allokeringsvillkor skapas för ett huvudkonto kommer systemet automatiskt att bokföra en ny verifikation när en verifikation som matchar ekonomiska källdimensionerna för allokeringsvillkoren bokförs.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]