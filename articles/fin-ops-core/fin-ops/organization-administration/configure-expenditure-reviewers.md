---
title: Konfigurera omkostnadsgranskare
description: I detta ämne beskrivs hur du använder utgiftsgranskare för att dynamiskt välja den användare som en arbetsflödesuppgift, ett godkännande eller ett manuellt beslut har tilldelats till.
author: rachel-profitt
ms.date: 06/25/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2021-06-24
ms.openlocfilehash: ad980889247e0239ad743078cb013c1c5839f676
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070156"
---
# <a name="configure-expenditure-reviewers"></a>Konfigurera utgiftsgranskare
[!include[banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Du kan ställa in dynamiska omkostnadgranskare att skicka utgifter till granskning baserat på antingen den användare som tilldelats en projektroll eller den ekonomisk dimension där omkostnaden debiteras. Arbetsflödeprocessen använder den angivna ägaren av projektrollen eller ekonomiska dimensionen för att bestämma vem skicka omkostnaden till.

När du skapar ett arbetsflöde kan du definiera en eller flera konfigurationer för omkostnadgranskare och sedan välja en konfiguration. Du kan konfigurera värdena för omkostnadgranskare för respektive juridisk person i din organisation. När du har definierat konfigurationer för omkostnadgranskare tilldelar du konfigurationen. Utgiftsgranskare kan tilldelas till arbetsflödesuppgifter, godkännanden och manuella beslut.

> [!NOTE]
> Även om utgiftsgranskningare inte är obligatoriska kan de förenkla konfigurationen av arbetsflödet. Du behöver till exempel inte skapa ett villkorsbeslut att kontrollera för varje kostnadsställedimension och sedan skapa ytterligare ett element för att tilldela godkännandet eller uppgiften till en viss användare eller användargrupp. Istället kan du konfigurera ägaren till kostnadsställedimensionen och använda en utgiftsgranskare för att dynamiskt välja rätt användare. När ägarskap eller tilldelning av kostnadsställen ändras måste du på detta sätt bara uppdatera fältet **Ägare** för den ekonomiska dimensionen.

## <a name="types-of-expenditure-reviewers"></a>Typert av omkostnadsgranskare

Alla arbetsflöden har inte stöd för begreppet "utgiftsgranskare". Du kan som standard konfigurera utgiftsgranskare för inköpsrekvisitioner, inköpsorder, leverantörsfakturor och utgiftsrapporter. För varje arbetsflödestyp måste du konfigurera utgiftsgranskarna på en separat sida som är specifik för funktionen och modulen. För varje dokument som stöds kan utgiftsgranskare användas med antingen arbetsflöden på rubriknivå eller med arbetsflöden på radnivå.

Följande tabell visar vart du går för att konfigurera en utgiftsgranskare för varje dokument som stöds.

| Dokument | Navigeringssökväg |
|----------|-----------------|
| Utgiftsrapporter | Utgiftshantering \> Konfiguration \> Policyer \> Utgiftsgranskare |
| Inköpsorder | Anskaffning och källa \> Konfiguration \> Policyer \> Utgiftsgranskare för inköpsorder |
| Inköpsrekvisitioner | Anskaffning och källa \> Konfiguration \> Policyer \> Utgiftsgranskare för inköpsrekvisition |
| Leverantörsfakturor | Leverantörsreskontra \> Policykonfiguration \> Utgiftsgranskare för leverantörsfaktura |

## <a name="expenditure-reviewer-assignments"></a>Tilldelningar för utgiftsgranskare

Två typer av tilldelningar är tillgängliga för respektive utgiftsgranskare: *projektfördelningar* och *organisationsfördelningar*. För en projektfördelning kan du välja mellan projektmyndigheter och ekonomiska dimensioner. För en organisationsfördelning kan du välja ekonomiska dimensioner.

Projektets beslutsfattare omfattar projektledare, projektkontrollant och projektförsäljningschef. Du definierar dessa beslutsfattare direkt i ditt projekt genom att välja en medarbetare i lämpliga fält.

Ekonomiska dimensioner styrs av kontostrukturerna i respektive juridisk person. För varje juridisk person kan du välja vilka ekonomiska dimensioner som ska användas med utgiftsgranskaren. Dimensionerna kan antingen komma från projektet (i det här fallet väljer du dimensionerna på fliken **Projektfördelningar**) eller dokumentet (i detta fall väljer du dimensionerna på fliken **Organisationsfördelningar**). I fältet **Ägare** på sidan **Värden för ekonomiska dimensioner** kan du välja medarbetare för respektive ekonomisk dimension.

## <a name="example-1-expenditure-reviewers-based-on-organization-distributions"></a>Exempel 1: Utgiftsgranskare baserat på organisationsfördelningar

Du arbetar för Contoso hushållsmaskiner, och organisationen har sex avdelningar och tio kostnadsställen. När en ny inköpsrekvisition skickas, måste godkännandet först komma från avdelningschefen och sedan från kostnadsställechefen.

I detta exempel konfigurerar du två *utgiftsgranskare för inköpsrekvisition*:

- För den första granskaren anger du avdelningen och väljer sedan den ekonomiska dimensionen **Avdelning** på fliken **Organisationsfördelningar**. 
- För den andra granskaren anger du kostnadsstället och sedan den ekonomiska dimensionen **Kostnadsställe** på fliken **Organisationsfördelningar**.

När du konfigurerar arbetsflödet skapar du två godkännandesteg. Det första gäller för avdelningen och den andra för kostnadsstället. För varje godkännandeelement väljer du **Deltagare** i fältet **Tilldelningstyp** på fliken **Rollbaserad**, därefter **Omkostnadsdeltagare** i fältet **Deltagartyp** och sedan tillhörande deltagare i fältet **Deltagare**.

När inköpsrekvisitionen skapas tilldelas avdelningen och kostnadsställets ekonomiska dimensioner till raderna i inköpsrekvisitionen. När arbetsflödet skickas utvärderar systemet först avdelningen på inköpsrekvisitionen och tilldelar godkännandeelementet till den användare som är kopplad till den medarbetare som du valde för avdelningen. När det första godkännandesteget har godkänts utvärderar systemet det andra godkännandesteget och tilldelar sedan det andra godkännandeelementet till den användare som är kopplad till den medarbetare som du valde för kostnadsstället.

## <a name="example-2-expenditure-reviewers-based-on-project-distributions"></a>Exempel 2: Utgiftsgranskare baserat på projektfördelningar

Du arbetar för tjänsteavdelningen på Contoso hushållsmaskiner. Organisationen kräver att projektledaren för respektive inköpsorder måste godkänna utgiften. Dessutom måste kostnadsställechefen för projektet godkänna den. Godkännandena kan utföras samtidigt. Båda användare måste hur som helst godkänna inköpsordern innan arbetsflödet kan fortsätta.

För detta exempel skapar du en *utgiftsgranskare för inköpsorder* som får namnet **PM och kostnadsställe**. Du markerar kryssrutan **Projektledare** och anger alternativet **Kostnadsställedimension** som **Ja** på fliken **Projektfördelningar** på sidan **Omkostnadsgranskare för inköpsorder**. Som en del av konfigurationen måste du se till att fältet **Projektledare** är inställt för alla projekt och att en ägare anges för alla kostnadsställen på sidan **Värden för ekonomisk dimension**.

När du konfigurerar arbetsflödet behöver du ett godkännandeelement. Du väljer **Deltagare** i fältet **Tilldelningstyp**. På fliken **Rollbaserad** väljer du sedan **Omkostnadsdeltagare** i fältet **Deltagartyp** och väljer sedan projektledare och kostnadsställe i fältet **Deltagare**. Om du vill vara säker på att arbetsflödet inte kan fortsätta förrän både projektledaren och ägaren av kostnadsstället har godkänt arbetsflödet, ställer du in fältet **Slutförandepolicy** som **Alla godkännare**.

När inköpsordern skapas måste fältet **Projekt** anges. Om du inte behöver ett projekt för alla dina inköpsorder bör du lägga till ett villkorsbeslut i arbetsflödet som kontrollerar om projektet finns i det innan godkännandesteget körs. Därefter utvärderas projektet som har angetts för inköpsordern av systemet, och godkännandeelementet tilldelas till användaren som är relaterad till medarbetaren i fältet **Projektansvarig**. Dessutom skapar systemet en uppgift och tilldelar den till den användare som är relaterad till den medarbetare som du väljer i fältet **Ägare** för kostnadsstället från projektet. Observera att detta exempel använder kostnadsstället för projektet, inte inköpsorderns kostnadsställe.

## <a name="set-up-expenditure-reviewers"></a>Konfigurera omkostnadsgranskare

Detta exempel visar hur du konfigurerar en omkostnadsgranskare för inköpsrekvisition. Om du vill konfigurera andra typer av omkostnadsgranskare ersätter du navigeringssökvägen i steg 1 med lämplig sökväg från tabellen i avsnittet [Typer av omkostnadsgranskare](configure-expenditure-reviewers.md#types-of-expenditure-reviewers) tidigare i det här ämnet.

1. Gå till **Anskaffning och källa \> Konfiguration \> Policyer \> Omkostnadsgranskare för inköpsrekvisition**.
2. På sidan **Omkostnadsgranskare för inköpsrekvisition** väljer du **Ny**.
3. I fältet **Namn** anger du ett namn för konfigurationen för omkostnadsgranskare, till exempel **kostnadsställe**.
4. På snabbfliken **Omkostnadsgranskare efter juridisk person** väljer du den juridiska person du vill konfigurera.
5. För en projektdistribution markerar du kryssrutan för respektive projektbeslutsfattare samt väljer **Ja** för varje ekonomisk dimension som du vill aktivera. 
6. För organisationsfördelningar: På fliken **Organisationsfördelningar** väljer du **Ja** för respektive ekonomisk dimension du vill aktivera.
7. Upprepa steg 4 till och med 6 för varje ytterligare juridisk person.

## <a name="assign-owners-to-financial-dimensions"></a>Tilldela ägare till ekonomiska dimensioner

Följ dessa steg för att tilldela en ägare till en ekonomisk dimension.

1. Gå till **Redovisning \> Kontoplan \> Dimensioner \> Ekonomiska dimensioner**.
2. Välj den ekonomiska dimension som ägaren ska tilldelas i listan.
3. Välj **Dimensionsvärden**.
4. Välj **Redigera** om du vill ändra dimensionsvärdena.
5. Välj det dimensionsvärde som en ägare ska tilldelas till i listan.
6. I fältet **Ägare** väljer du den medarbetare du vill tilldela dimensionsvärdet till.

## <a name="configure-project-distributions"></a>Konfigurera projektfördelningar

Följ dessa steg om du vill tilldela beslutsfattare till ett visst projekt:

1. Gå till **Projekthantering och redovisning \> Projekt \> Alla projekt**.
2. Välj det projekt som du vill tilldela beslutsfattare till.
3. Välj **Redigera** om du vill ändra projektet.
4. På snabbfliken **Allmänt**, i avsnittet **Ansvarig**, väljer du en medarbetare för fälten **Försäljningschef**, **Projektansvarig** och **Projektkontrollant**.
5. På snabbfliken **Ekonomiska dimensioner** väljer du de ekonomiska dimensioner som krävs för projektet.

## <a name="assign-expenditure-reviewers-to-a-workflow-task"></a>Tilldela omkostnadgranskare till en arbetsflödesuppgift

Det här exemplet visar hur du konfigurerar ett arbetsflöde för inköpsrekvisitioner så att det använder en omkostnadsgranskare för inköpsrekvisitioner. Om du vill konfigurera andra typer av arbetsflöden kan den arbetsflödessida som du måste öppna i steg 1 komma att finnas i modulen **Utgiftshantering** eller **Leverantörsreskontra** istället för modulen **Anskaffning och källa**.

Om du vill tilldela omkostnadsgranskare för en inköpsrekvisition till en arbetsflödesuppgift följer du dessa steg:

1. Gå till **Anskaffning och källa \> Inställningar \> Arbetsflöden för anskaffning och källa**.
2. Tryck två gånger (eller dubbelklicka) på ett befintligt arbetsflöde, eller skapa ett nytt arbetsflöde.
3. Välj uppgiften som du vill tilldela konfigurationen för omkostnadsgranskare till i fönstret **Arbetsflöde** i arbetsflödesredigeraren. I **Åtgärdsfönstret** > gruppen **Visa** väljer du sedan **Egenskaper**.
4. I det vänstra fönstret på sidan **Egenskaper** väljer du sedan **Tilldelning**.
5. På fliken **Tilldelningstyp** väljer du **Deltagare**.
6. På fliken **Rollbaserad**, i fältet **Deltagartyp**, väljer du **Omkostnadsdeltagare**. I fältet **Deltagare** väljer du sedan den konfiguration för omkostnadsgranskare som du vill användare för arbetsflödesuppgiften.
