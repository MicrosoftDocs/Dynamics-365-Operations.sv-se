---
title: Arbeta med mallar
description: I denna artikel beskrivs hur du arbetar med mallar i Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 02/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: cbe9d103da9c86dcf3aad54ec036282d2bb3faca
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282691"
---
# <a name="work-with-templates"></a>Arbeta med mallar

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du arbetar med mallar i Microsoft Dynamics 365 Commerce.

Som vi har diskuterat i [Översikt över mallar och layouter](templates-layouts-overview.md), mallar definierar vilka alternativ som är tillgängliga för författare av underordnade. Mallar är användbara för företagets webbredigeringsteam av många skäl och välstrukturerade mallar kan hjälpa dig med följande mål:

- Förenkla redigeringsupplevelsen för dagliga rollfunktioner för innehållsredigering.

    - Filtrera modulalternativ så att bara relevanta moduler visas för ett visst sidavsnitt. (Marknadsföringsavsnittet i en mall kan t.ex. konfigureras för att filtrera bort irrelevanta moduler som aldrig ska användas i det sammanhanget och som bara kan komplicera innehållsredigeringsuppgifter om de visas.)
    - Konfigurera standardmodulens inställning för att förbättra formens effektivitet.
    - Definiera standard sidfragment för att förbättra redigeringseffektiviteten. (Exempel: rubrik- och sidfotsavsnitt i en mall visas automatiskt på alla efterföljande sidor.)

- Behåll företagets webbplatser på varumärken genom att definiera en godkänd uppsättning modulers arrangemang och konfigurationsalternativ.

    > [!TIP] 
    > En lyckad näthandelssajt förser kunder med designmönster som är välbekanta, repeterbara och grundläggande användarupplevelse på varumärke (UX). Genom att använda mallar kan du kontrollera konsekvensen på webbplatsen.

- Förbättra SEO-poängen (sökmotoroptimering) genom att säkerställa repeterbara och programmässigt definierade siddefinitioner och metadata.

> [!NOTE]
> Även om mallar har utformats för att styra konsekvensen på en plats, kan de teoretiskt konfigureras så att de inte tvingar fram någon konsekvens. Varumärkes- och webbplatsadministratörer kan definiera valfri nivå av variabilitet för sidorna på webbplatsen. En mall kan till exempel vara helt öppen så att innehållsförfattarna kan skapa alla sidutformningar som de väljer. I detta fall gäller ingen av fördelarna i föregående lista.

## <a name="modify-a-template"></a>Ändra en mall

Mallarna ändras med hjälp av mallredigeraren.

Öppna mallredigeraren i Commerce-webbplatsbyggaren genom att följa något av följande steg:

- I navigeringsfönstret på din webbplats, välj **Mallar** och välj sedan den mall som du vill ändra.
- Markera den översta noden i dispositionsträdet till vänster i sidredigeraren för en befintlig sida. Välj sedan **Redigera mall** i egenskapsrutan till höger.

I dispositionsträdets vy till vänster visas de moduler och strukturer som är tillgängliga för underordnade layouter och sidor. När du väljer en modul i dispositionsträdet kan du visa mallegenskaper för den markerade modulen i egenskapsrutan till höger. Vissa av egenskaperna är unika när du redigerar mallar. I följande register beskrivs dessa egenskaper.

| Egenskapsnamn | Beskrivning |
|---|---|
| Minsta antal förekomster | Den här egenskapen definierar det minsta antalet förekomster för den valda modulen. Om värdet till exempel är inställt på **1**, krävs modulen för underordnade författare, men om värdet är **0** (noll) är modulen valfri. |
| Max antal förekomster | Den här egenskapen definierar det högsta antalet förekomster för den valda modulen. Om värdet till exempel är inställt på **1** kan modulen bara läggas till en gång. |
| Min moduler (behållare) | För moduler som innehåller andra moduler (dvs. för *behållarmoduler*) definierar denna egenskap det minsta antal moduler som ska läggas till som underordnade. För till exempel en karusellmodul kan värdet vara ett värde som är större än 1. |
| Max moduler (behållare) | Den här egenskapen definierar det maximala antalet moduler som ska läggas till som underordnade för behållarmoduler. För till exempel en karusellmodul kan värdet vara ett värde som är mindre än 10. |
| Låst | En **låst** boolesk kontroll visas bredvid alla kärnmodulegenskaper. Mallen gör att författaren kan låsa en modulinställning i mallen. En modulinställning som är låst kan inte åsidosättas av underordnade layouter eller sidor. Det blir ett centralt redigerbart egenskaps värde för alla layouter och sidor som använder mallen. |

## <a name="create-a-new-template"></a>Skapa en ny mall

För att skapa en ny mall i Commerce-webbplatsskaparen.

1. I navigeringsfönstret på din webbplats, välj **Mallar** för att öppna mallinspektörvyn.
1. Välj **Ny mall**.
1. I dialogrutan mallskapande, ange ett namn och en beskrivning för mallen. De värden du anger visas för författare när de skapar nya sidor. Ange därför metadata som är användbara för sidförfattare. Ange till exempel **Använd den här mallen om du vill skapa allmänna marknadsföringssidor** som beskrivning. Dessa metadata kan redigeras senare.
1. Klicka på **OK** om du vill skapa den nya mallen och öppna redigeraren. I mallredigeraren visas ett dispositionsträd till vänster och ett egenskapsfönster till höger.
1. I dispositionsträdet expanderar du noderna och väljer platsen **HTML-huvud**.
1. Om det ännu inte finns moduler på denna plats väljer du ellipsknappen (**...**) och välj sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul**, välj **Sammanfattning standardsida** och klicka sedan på **OK**.
1. Markera den nya modulen i dispositionsträdet och ange sedan de standardinställningar som ska konfigureras automatiskt för alla underordnade sidor i mallen i egenskapsfönstret. Om du inte vill ha några standardinställningar ska du lämna värdena tomma.
1. I dispositionsträdet väljer du platsen **Brödtext**, markerar ellipsknappen och väljer sedan **Lägg till modul**.
1. Välj en modul för sidbehållare (det kan bara finnas ett alternativ) och välj sedan **OK**.

Under den nya sidan för sidbehållare visas en ny uppsättning platser **(rubrik**, **huvud** och så vidare). Här kan du lägga till och konfigurera de modulalternativ som är tillgängliga för författare när de skapar sidor från den här mallen. Om du inte lägger till moduler till en plats kan alla tillgängliga typer av moduler användas för platsen.

Mallen är nu tekniskt giltig och kan sparas, checkas in och användas för att skapa nya sidor. I de följande tre avsnitten beskrivs emellertid några andra standardinställningar som du kanske vill konfigurera först.

## <a name="add-a-header-and-a-footer"></a>Lägg till sidhuvud och sidfot

Om det redan finns ett rubrik avsnitt för webbplatsen följer du dessa steg i webbplatsskaparen för att ett sidhuvud och en sidfot i en mall.

1. I dispositionsträdet expanderar du platsen **Brödtext** och den underordnade sidmodulen.
1. Markera platsen **rubrik**.
1. Markera knappen med punkter för platsen **rubrik** och välj sedan **Lägg till fragment**.
1. Sök efter och markera webbplatsens rubrikavsnitt och välj sedan **OK**.

Alla sidor som använder mallen ärver nu automatiskt detta rubrikfragment.

Om din webbplats ännu inte har ett rubrikavsnitt se [Skapa ett fragment](work-with-fragments.md#create-a-fragment) för information om hur du skapar det. Slutför sedan proceduren ovan.

## <a name="change-the-template-theme"></a>Ändra malltemat.

Om du vill ange standardtemat för alla sidor som använder en mall följer du stegen i webbplatsskaparen.

1. I dispositionsträdet till vänster expanderar du platsen **Brödstext**.
1. I platsen **Brödtext** väljer du sidan för sidbehållare (t.ex **standardsida**).
1. Välj ett tema i fältet **tema** i egenskapsfönstret till höger.

Alla nya sidor använder nu det valda temat som standard. Om du vill förhindra att sidorna åsidosätter den här inställningen på layout- eller sidnivå ställer du in booleska kontrollen **Låst** till **Sant**.

## <a name="add-a-script-to-a-template"></a>Lägga till ett skript i en mall

Du kan lägga till HTML **&lt;skript&gt;** element som innehåller JavaScript i din mall. På det här sättet kan du ange standardskriptbeteenden för HTML-rubrik, brödtextens början och brödtextens slut och avsnitt på sidorna.

Om du vill lägga till ett skript på en mall i webbplatsskaparen följer du stegen nedan.

1. I dispositionsträdet till vänster väljer du den plats där du vill lägga till **&lt;skript&gt;** elementet (t.ex. HTML-rubrik, brödtextens början eller brödtextens slut).
1. Markera knappen med punkter för platsen och välj sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul** välj en skriptmodul (till exempel, **externt skript** eller **infogat skript**).
1. I egenskapsrutan till höger, skriv lämplig skript egenskapskontroll (t.ex. **infogat skript** eller **skripttaggar**).
1. Ange eventuella ytterligare inställningar som du vill konfigurera i egenskapsrutan.

> [!TIP]
> Om du vill återanvända någon av dina skriptfiler för andra mallar kan du konvertera dem till fragment. På det här sättet kan du göra redigeringsprocessen mer effektiv och du centraliserar uppdateringsprocessen. Information om hur du konverterar en skriptfil till ett fragment finns i [Spara en befintlig modulkonfiguration som ett fragment](work-with-fragments.md#save-an-existing-module-configuration-as-a-fragment).

## <a name="save-check-in-preview-and-publish-a-template"></a>Spara, checka in, förhandsgranska och publicera en mall

Om du vill spara och checka in en mall i webbplatsskaparen, följ dessa steg.

1. Välj **spara** längst upp i mallredigeraren. Sparade ändringar påverkar inte underordnade sidor förrän de checkas in.
1. Välj **Slutför redigering**. Dina ändringar kan nu upptäckas för efterföljande arbetsflöden.

Om du vill förhandsgranska ändringarna öppnar du en befintlig sida som använder mallen eller skapar en ny sida från mallen.

När du har förhandsgranskat ändringarna i din mall gör du följande för att publicera mallen på din aktiva webbplats:

* Gå till **mallar**, markera mallen och välj sedan **publicera**.
* Välj layoutnamn för att öppna layoutredigeraren och välj sedan **Publicera**.
* Publicera en sida som refererar till den opublicerade mallen. Mallen publiceras automatiskt.

> [!WARNING]
> När en mall, eller något annat CMS-objekt (innehållshanteringssystem), publiceras, kan den upptäckas på Internet. Publicera inte dokument eller resurser förrän du är redo att göra dem offentlig. Dokumentversioner som har sparats och checkats in, men som inte har publicerats, är endast synliga för autentiserade systemanvändare.

## <a name="rename-a-template"></a>Byt namn på en mall

Följ dessa steg för att byta namn på en befintlig mall i webbplatsskaparen.

1. I navigeringsfönstret till vänster välj er du **Mallar**.
1. Välj mallnamnet för mallen som du vill byta namn på.
1. Välj **Redigera** för att börja redigera mallen. Observera att du inte kan redigera en mall om någon annan redan redigerar en mall.
1. I rutan för mallegenskaper väljer du pennsymbolen bredvid mallnamnet.
1. Redigera mallnamnet efter behov.
1. Markera kryssrutan om du vill bekräfta namnändringen.
1. Välj **Slutför redigering**.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över mallar och layouter](templates-layouts-overview.md)

[Arbeta med förinställda layouter](work-with-layouts.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
