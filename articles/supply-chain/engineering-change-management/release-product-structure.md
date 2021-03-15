---
title: Frisläppa produktstrukturer
description: I det här avsnittet beskrivs hur du kan frigöra kompletta produktstrukturer, förutom att frigöra produkter tillsammans med deras tekniska versioner. På det här sättet kan du se till att teknikerrelevanta produktdata enkelt kan återanvändas i olika juridiska enheter.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgProductReleaseSiteBulkEdit, EngChgProductReleaseSendListPage, EngChgProductReleaseSendDetails,EngChgProductReleaseSelection,EngChgProductReleaseReceiveListPage, EngChgProductReleaseReceiveDetails, EngChgProductReleasePreviewPane, EngChgProductReleasePolicy, EngChgProductReleasePart, EngChgProductReleaseNote
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 971ff16b862a48581365523edc6b64052b29c380
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967242"
---
# <a name="release-product-structures"></a>Frisläppa produktstrukturer

[!include [banner](../includes/banner.md)]

För att säkerställa att de tekniska produktdata lätt kan återanvändas i olika juridiska personer kan du frigöra kompletta produktstrukturer utöver att frigöra produkter tillsammans med deras tekniska versioner. Därför kan du släppa strukturlistor i flera nivåer tillsammans med den överordnade i en enda frisläppningsåtgärd. I det här fallet frigörs även strukturlistan och de lägre produkterna.

Tekniska produkter skapas och underhålls av deras teknikföretag på ett sådant sätt att de uppfyller kvalitets kraven när de har utformats. Varje operationellt företag som tillverkar en produkt behöver samma produkt och underliggande strukturlista. Beroende på produktionsfunktionen kan flödet skapas lokalt. I detta fall frigörs inte en rutt tillsammans med produkten. För juridiska personer som ska sälja produkterna men inte tillverka dem, kanske strukturlistan inte behövs.

För att processen ska bli mer effektiv kan alla tekniska data frisläppas till andra operationella företag samtidigt. Dessa data inkluderar produktstrukturen. Under frisläppningsprocessen kan du välja vilken del av produktdata som ska frisläppas.

För mer information om teknikföretag och operativa företag, se [Dataägarskapsregler för teknikföretag](engineering-org-data-ownership-rules.md).

Observera att du kan frisläppa både standardprodukter och tekniska produkter tillsammans med den frisläppta produktstrukturen. Under den här processen frigörs hela produktstrukturen, även strukturlistan och flödet från företaget som produkterna frigörs i.

Ett exempel på hur du frigör en produkt finns i [frisläppa en teknisk produkt i ett lokalt företag](engineering-scenarios.md#release)

## <a name="released-data-for-a-product-when-the-release-product-structure-is-used"></a>Frisläppta data för en produkt när produktstrukturen för frisläppning används

Följande data ingår i frisläppningen av tekniska produkter:

- **Produktdata** – en ny frisläppt produkt skapas.
- **Teknisk versionsinformation** – tekniska versionen och dess data skapas eller uppdateras. Observera att om du släpper samma tekniska version igen på ett fungerande företag, kommer de tekniska data att skrivas över.
- **Tekniska attribut** – de tekniska attributen och deras värden skapas och uppdateras.
- **Teknisk struktur** – den tekniska strukturlistan och dess rader kan skapas och uppdateras. Mer information om dataägande, se [Produktägare](product-owner.md).
- **Tekniska rutter** – de tekniska rutterna och deras åtgärder kan skapas och uppdateras. Mer information om dataägande, se [Produktägare](product-owner.md).
- **Tekniska dokument** – tekniska dokument som är anslutna till tekniska versionen skapas eller uppdateras.

När du aktiverar konstruktionsändringshantering i systemet är produktstrukturen för frisläppning tillgänglig. Dessutom inkluderar standardprodukter deras strukturlistor och flöden när de frigörs.

## <a name="product-acceptance"></a>Produktgodkännande

**Produktgodkännande** är en nyckelparameter som påverkar utgivningsprocessen. Du kan ställa in den här parametern för varje företag genom att gå till **Konstruktionsändringshantering \> Konfiguration \> Parametrar för ändringshantering**. Mer information finns i [parametrar för konstruktionsändringshantering](engineering-parameters.md).

### <a name="automatic-product-acceptance"></a>Automatisk produktmottagning

Varje utgåva av tekniska produkter startar när någon från tekniska företaget väljer en produkt som ska frisläppas. När parametern **produktacceptans** anges till *automatisk* bestämmer användaren vid det tekniska företaget automatiskt vilka produktdata som automatiskt ska frisläppas till driftsföretagen. Produkten frisläpps sedan automatiskt till företagen som väljs i frisläppningsguiden.

### <a name="manual-product-acceptance"></a>Manuell produktmottagning

Varje utgåva av tekniska produkter startar när någon från tekniska företaget väljer en produkt som ska frisläppas. När parametern **produktacceptans** anges till *manuell* bestämmer användaren vid det tekniska företaget automatiskt vilka produktdata som automatiskt ska frisläppas till driftsföretagen. En användare från varje driftsföretag granskar sedan produktdata och bestämmer om du vill acceptera utsättningen. Användaren på operationella företaget kan ställa in följande alternativ när data tas emot:

- Om produkterna (uppdateringar) inte är relevanta för det operativa företaget kan användaren välja att inte godkänna frisläppningen.
- Användaren kan ändra artikelmallen för nya produkter.
- Användaren kan välja om produkten ska frisläppas tillsammans med deras strukturlistor och/eller flöden och om de ska frisläppas som godkända och aktiva.
- Användaren kan ändra produkternas startdatum.

Ett exempel på hur du accepterar en produkt finns i [Granska och acceptera produkten innan du släpper den i det lokala företaget](engineering-scenarios.md#accept).

> [!NOTE]
> För standardprodukter kan du släppa från alla juridiska enheter till andra juridiska enheter. För tekniska produkter är den enda juridiska person som du kan lansera från är det tekniska företaget.

## <a name="release-policies"></a>Utgivningsprinciper

Alla operativa företag behöver inte ha samma produkt data. I allmänhet kräver drift företag som tillverkar tekniska produkter en strukturlista, medan operativa företag som bara säljer tekniska produkter behöver inte ha en strukturlista. Du kan använda frisläppnings principer för att fastställa vilka parametrar som används för frisläppning av produkt.

För tekniska produkter tilldelas frisläppningspolicyn i kategorin teknisk produkt, och fältet är obligatoriskt. För standardprodukter tilldelas policyn till den delade produkten, och fältet är valfritt.

Mer information om tekniska produktkategorier finns i [Konstruktionsversioner och kategorier av konstruktionsprodukter](engineering-versions-product-category.md).

Under frisläppningsprocessen kan du påverka inställningarna.

## <a name="create-and-manage-product-release-policies"></a>Skapa och hantera principer för produktfrisläppning

För att arbeta med policyer för produktfrisläppning, gå till **Konstruktionsändringshantering \> Inställning \> Principer för produktfrisläppning**. Gör sedan något av följande.

- Om du vill skapa en ny policy väljer du **ny** i åtgärdsfönstret och anger sedan fälten enligt beskrivningen i följande underavsnitt.
- Om du vill redigera en befintlig policy markerar du den i listvyn, väljer **Redigera** i åtgärdsfönstret och anger sedan fälten enligt beskrivningen i följande underavsnitt.
- Om du vill ta bort en befintlig policy markerar du den i listfönstret och väljer du **Redigera** i åtgärdsfönstret och sedan på snabbfliken **Allmänt** ser du till att alternativet **Aktiv** anges till *Nej*. Välj sedan **Ta bort** i åtgärdsfönstret.

### <a name="header"></a>Siduvud

Ange följande fält i rubriken för en policy produktfrisläppning.

| Fält | beskrivning |
|---|---|
| Namn | Ange ett namn på policy. |
| beskrivning | Ange en beskrivning för policyn. |

### <a name="general-fasttab"></a>Snabbfliken Allmänt

Ange följande fält i snabbfliken **Allmänt** i en produktfrisläppningspolicy.

| Fält | beskrivning |
|---|---|
| Produkttyp | Välj om policyn gäller för produkter av typen *artikel* eller *tjänst*. Du kan inte ändra den här inställningen när du har sparat posten. |
| Använd mallar | Välj ett av följande alternativ för att ange om och hur mallar för produktfrisläppningsmallar ska användas när en princip används:<ul><li>**Alltid** – en av de frisläppta produkterna måste alltid användas för frisläppning. Om du väljer det här alternativet använder du snabbfliken **Alla produkter** för att ange den mall som används för varje företag som du släpper upp till. Om du inte anger en mall för varje företag som visas på snabbfliken **Alla produkter** visas ett felmeddelande när du försöker spara policyn.</li><li>**Valfri** – om en frisläppt produkt har angetts för ett företag som anges på snabbfliken **Alla produkter** kommer den mallen att användas när du släpper upp det företaget. Annars kommer ingen mall att användas. Om du väljer det här alternativet kan du spara policyn utan att tilldela mallar till alla företag. (Ingen varning visas.)</li><li>**Aldrig** – Ingen frisläppt produkt kommer att användas för alla företag som du frisläpper till, även om en mall anges för företag som är listad på snabbfliken **Alla produkter**. Mallkolumner kommer inte att vara tillgängliga.</li></ul> |
| Aktiva | Använd det här alternativet för att upprätthålla dina frisläppningsprinciper. Ange värdet *Ja* för alla frisläppningsprinciper som du använder. Ställ in den på *Nej* för att markera att en frisläppningsprincip är inaktiv när den inte används. Observera att du inte kan inaktivera en frisläppningsprincip som är tilldelad en teknisk produktkategori, och du bara kan ta bort inaktiva frisläppningsprinciper. |

### <a name="all-products-fasttab"></a>Snabbfliken alla produkter

På snabbfliken **Alla produkter** lägger du till en rad för varje operativt företag som du vill använda den här principen för. Använd knappar på snabbfliken **Alla produkter** om du vill lägga till och ta bort rader som du behöver. Ange följande fält för varje rad du lägger till.

> [!NOTE]
> Inställningarna på snabbfliken **Alla produkter** gäller för produkter och standardprodukter som är tekniska produkter.

| Fält | beskrivning |
|---|---|
| ID för företagskonton | Välj det företag som raden gäller för. Parametrarna på raden tillämpas när produkter frisläpps till det här företaget. |
| Mall för släppt produkt | Lägg till en mall för produkten. |
| Kopiera strukturlistegodkännande | Markera den här kryssrutan om du vill kopiera strukturlistans godkännandestatus till det mottagande företaget. |
| Kopiera strukturlistans aktivering | Markera den här kryssrutan om du vill kopiera strukturlistans aktiveringsstatus till det mottagande företaget. |
| Kopiera flödesgodkännande | Markera den här kryssrutan om du vill kopiera strukturlistans ruttstatus till det mottagande företaget.|
| Kopiera flödesaktivering | Markera den här kryssrutan om du vill kopiera strukturlistans aktiveringsstatus till det mottagande företaget. |

### <a name="option-parameters-for-engineering-products-fasttab"></a>Alternativparametrar för snabbfliken tekniska produkter

Varje gång du lägger till en rad på snabbfliken **alla produkter** skapas även en rad som har ett matchande **företags konto-ID** på snabbfliken **Alternativparametrar för tekniska produkter**. Om du tar bort en rad från snabbfliken **alla produkter** tas även en rad som har ett matchande **företags konto-ID** bort på snabbfliken **Alternativparametrar för tekniska produkter**.

För varje rad som visas på snabbfliken **Alternativparametrar för tekniska produkter** anger du följande fält.

> [!NOTE]
> Inställningarna på snabbfliken **Alternativparametrar för tekniska produkter** gäller bara för tekniska produkter.

| Fält | beskrivning |
|---|---|
| Mallstrukturlista | När en produkt som har en strukturlista släpps, kommer raderna i den angivna mallstrukturlistan att läggas till. Det här fältet är användbart när du vill lägga till lokala komponenter, t.ex. förpackning eller instruktioner på det lokala språket. |
| Mallflöde | När en produkt som har en rutt släpps, kommer raderna i den angivna mallen att läggas till. |
| Kopiera effektivitet | Välj om du vill kopiera effektivt datum från tekniska företaget till det operativa företaget när du släpper produkter. |
| Lägg automatiskt till i släppförslag | Markera den här kryssrutan för produkter som automatiskt ska frisläppas på teknisk ändringsorder. På detta sätt kan produkter som tillhör kategorier av konstruktionsprodukter som använder den här versionen automatiskt frisläppas till operativt företag där det här alternativet har ställts in. (För mer information, se [Hantera ändringar av konstruktionsprodukter](engineering-change-management.md)).

### <a name="review-each-product-when-you-release-it"></a>Granska varje produkt när du släpper den

När tekniska produkter som har strukturlistor eller flöden frigörs, kommer parametrarna att ställas in som standardvärden enligt beskrivningen i frisläppningspolicyn. Som användare kan du påverka det här beteendet på frisläppningssidan när du använder produktstrukturen för frisläppning.

Om du vill frisläppa tekniska produkter **Frisläppta produkter** välj de produkter som ska släppas och välj sedan **Frisläppa produktstruktur** för att öppna frisläppningsguiden. På sidan **Välj tekniska produkter att frisläppa** visas produkterna. Välj en enskild produkt och välj sedan **frisläppningsinformation** för att granska frisläppningsinformation för produkten.

På sidan **frisläppningsdetaljer** kan du ändra värdet för fälten **Ta emot strukturlista**, **Kopiera godkännande av strukturlista**, **Kopiera aktivering av strukturlista**, **Ta emot strukturlista**, **Kopiera godkännande av rutt** och **Kopiera aktivering av flöde**. I flyttningsscenariot kan du ändra värdet för samma fält på mottagarsidan, förutsatt att strukturlistan och flödet har frisläppts.

## <a name="product-owners-and-product-releases"></a>Produktägare och produktlanseringar

Eftersom produktägare vet vilka juridiska personer som behöver sina produkter kan en produkt endast frisläppas av medlemmarna i produktens ägargrupp. Andra användare kan inte frisläppa produkter som de inte äger.

Det här problemet gäller bara när en produkt väljs direkt för frisläppning. Produkter som ingår i en annan produkts struktur via en strukturlista *kan* frisläppas av användare som inte är ägare när de släpper upp den överordnade produkten, förutsatt att de äger den överordnade produkten.

Produktens X tilldelas till exempel produktens ägargruppen *Designa skåp*. Produkt X ingår även i strukturlistan för produkt Y, som tilldelas produktägargruppen *Designa högtalare*. Om en användare från en produktägargrupp *Designa högtalare* frisläpper produkt Y och dess strukturlista, frisläpps produkt X tillsammans med produkt Y.

Mer information finns i [Produktägare](product-owner.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]