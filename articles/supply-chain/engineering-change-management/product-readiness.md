---
title: Produktberedskap
description: I denna artikel beskrivs hur du kan använda beredskapskontroller för att säkerställa att erforderliga huvuddata har slutförts för en produkt innan de används i transaktioner.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a8e76d5fc786b6f4cac7cd0430399ca3ad13a7bc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856234"
---
# <a name="product-readiness"></a>Produktberedskap

[!include [banner](../includes/banner.md)]

Du kan använda beredskapskontroller för att säkerställa att alla nödvändiga huvuddata har specificerats för en produkt innan de används i transaktioner. När beredskapskontroller används blir en användare eller ett team ansvarigt för att validera specifika fördefinierade produktspecifika data.

Du kan markera kryssrutan **Aktiv** för en teknisk produkt, variant eller version efter att alla nödvändiga data har angetts och verifierats och efter att alla beredskapskontroller har bearbetats. Om en eller flera kontroller inte har bearbetats för produkten, versionen eller varianten, när du försöker markera kryssrutan **Aktiv** du får en varning om att inte alla kontroller har slutförts.

Du kan skapa beredskapskontroller för nya produkter, varianter och konstruktionsversioner. Du kan också utföra beredskapskontroller på standardprodukter (icke-tekniska) produkter (se också [Beredskapskontroller för standardprodukter](#standard-products)). 

Du kan använda standardprodukter i transaktioner även om inte alla beredskapskontroller har slutförts. Om du behöver spärra en produkt från att användas i transaktioner, använd dess livscykelläge. Du kan tilldela en livscykelstat som spärrar en produkt från att användas i transaktioner och sedan, när alla beredskapskontroller har slutförts, tilldela en ny livscykelstat som tillåter nödvändiga transaktioner.

## <a name="types-of-readiness-checks"></a>Typer av beredskapskontroller

Det finns tre typer av beredskapskontroller:

- **Systemkontroll** – systemet kontrollerar om det finns en giltig post. Posten kan till exempel vara en aktiv strukturlista.
- **Manuell kontroll** – en användare verifierar om posten är giltig. En beredskapskontroll kan till exempel kräva validering av standard orderinställningarna. I vissa fall, t.ex. när produkten fortfarande är konstruerad och därför inte kommer att placeras i lager, krävs inga standard orderinställningar. Standard orderinställningar kan dock krävas för en annan produkt av samma typ, eftersom produkten kan hållas i lager. Användaren är ansvarig för att veta hur du korrekt fattar beslut om en beredskapskontroll krävs.
- **Kontrollista** – användaren svarar på en serie frågeställningar från en kontrollista och systemet avgör om svaren möter förväntningarna. Kontrollistan kan ha vilket ämne som helst. Det kan till exempel användas för att avgöra om marknadsföringsmaterial eller produktdokumentation är slutförd.

<a name="checks-engineering"></a>

## <a name="how-readiness-checks-are-created-for-a-new-engineering-product-variant-or-version"></a>Hur beredskapskontroller skapas för en ny teknisk produkt, variant eller version

(Policyer för beredskapskontroll kan användas på den frisläppta produktnivån, den släppta variantnivån och teknisk versionsnivån).

När du skapar en ny *teknikprodukt* bestämmer systemet om en [beredskapskontrollpolicy gäller](#assign-policy) för den. Om en policy för beredskapskontroll används inträffar följande händelser:

- Beredskapskontroller skapas för produkten enligt tillämplig policy.
- Tekniska versionen är inaktiverad för att blockera produkten från att användas. Alla tekniska versioner för produkten är inställda på inaktiv.

Om en ny *variant* skapas för en produkt kontrollerar systemet om en kontrollpolicy för beredskap gäller för den. (Beredskapskontroller kan användas på den frisläppta variantnivån och teknisk versionsnivån). Om en policy gäller inträffar följande händelser:

- Beredskapskontroller skapas för produkten enligt tillämplig policy.
- Tekniska versionen och variant är inaktiverad för att blockera produkten från att användas.

Om en ny teknisk *version* skapas för en produkt kontrollerar systemet om en kontrollpolicy för beredskap gäller för den. (Beredskapskontroller kan användas på den tekniska versionsnivån). Om en policy gäller inträffar följande händelser:

- Beredskapskontroller skapas för produkten enligt tillämplig policy.
- Tekniska versionen är inaktiverad för att blockera produkten från att användas.

> [!NOTE]
> Du kan också konfigurera policyer för beredskapskontroller på standardprodukter (icke-tekniska). Mer information finns i avsnittet [Beredskapskontroller för standardprodukter](#standard-products) längre fram i denna artikel.

## <a name="view-readiness-checks"></a>Visa beredskapskontroller

### <a name="view-open-readiness-checks-for-a-product-or-product-version"></a>Visa öppna beredskapskontroller för en produkt eller produktversion

Om du vill hitta de öppna beredskapskontrollerna för en produkt öppnar du sidan **information om frisläppta produkter**. I åtgärdsfönstret, på fliken **Produkt**, i gruppen **Beredskapskontroller**, markerar du sedan **Beredskapskontroller**.

Om du vill hitta de öppna beredskapskontrollerna för en produktversion öppnar du sidan **tekniska versioner** för en frisläppt produkt och väljer en version. I åtgärdsfönstret, på fliken **Produkt**, i gruppen **Kontrollista**, markerar du sedan **Beredskapskontroller**.

### <a name="view-open-readiness-checks-that-are-assigned-to-you"></a>Visa öppna beredskapskontroller som har tilldelats dig

Följ de här stegen om du vill visa de öppna beredskapskontroller som har tilldelats dig.

- Gå till **Konstruktionsändringshantering \> Gemensamt \> Produktberedskap \> Mina öppna beredskapskontroller**.
- Gå till **Produktinformationshantering \> Arbetsytor \> Produktberedskap för diskret tillverkning**.

Den inställning som anger vem en beredskapskontroll är tilldelad för den beredskapspolicyn. Beredskapskontroller kan tilldelas en person eller ett team. Om en beredskapskontroll tilldelas till ett team finns det en person i teamet som måste bearbeta beredskapskontrollen.

## <a name="process-open-readiness-checks"></a>Bearbeta öppna beredskapskontroller

### <a name="process-system-and-manual-readiness-checks"></a>Bearbeta system- och manuella beredskapskontroller

När du har öppnat **beredskapskontroller** du kan visa ämnet för system- och manuella beredskapskontroller genom att välja **Visa relaterad information** i åtgärdsfönstret. Du kan sedan slutföra och/eller validera data för beredskapskontrollen. Öppna beredskapskontroller har **status** värdet *väntar*. Denna status anger att beredskapskontrollen fortfarande måste bearbetas. Följ ett av dessa steg för att bearbeta en beredskapskontroll.

- I åtgärdsfönstret, välj **kontrollera/slutföra** för att granska och slutföra beredskapskontrollen. När du är klar uppdateras fältet **Status** till *Godkänd*.
- Välj hoppa över i åtgärdsfönstret, välj **Hoppa över** om du vill hoppa över en beredskapskontroll som inte är obligatorisk. Du kan till exempel konfigurera en beredskapskontroll för prisberäkningar. Du väljer dock att hoppa över den här kontrollen medan produkten fortfarande är i designfasen. I det här fallet uppdateras fältet **Status** till *Överhoppad*.

Beroende på konfigurationen av beredskapsprincipen, när fältet **Status** för beredskapskontroll har uppdaterats till *godkänd*, ett extra steg kan krävas för att godkänna beredskapskontrollen. I det här fallet väljer du **godkännande** för att slutföra beredskapskontrollen. Det här godkännandesteget är alltid obligatoriskt när beredskapskontrollen hoppas över.

När alla öppna beredskapskontroller för en ny produkt, variant eller version har bearbetats och godkänts efter behov, blir objektet automatiskt aktivt och kan därför användas.

### <a name="process-checklist-readiness-checks"></a>Bearbeta checklista beredskapskontroller

Öppna en checklista genom att öppna sidan **beredskapskontroller** och sedan välja **Starta checklista** i åtgärdsfönstret. När du har slutfört checklistan validerar systemet om beredskapskontrollen har passerats, baserat på inställningarna i enkäten. Om checken överförs uppdateras fältet **Status** uppdateras till *Godkänd*. Om beredskapskontrollen inte är obligatorisk kan du hoppa över den. I det här fallet uppdateras fältet **Status** till *Överhoppad*.

Beroende på konfigurationen av beredskapsprincipen, när fältet **Status** för beredskapskontroll har uppdaterats till *godkänd*, ett extra steg kan krävas för att godkänna beredskapskontrollen. I det här fallet väljer du **godkännande** för att slutföra beredskapskontrollen. Det här godkännandesteget är alltid obligatoriskt när beredskapskontrollen hoppas över.

När alla öppna beredskapskontroller för en ny produkt, variant eller version har bearbetats och godkänts efter behov, blir objektet automatiskt aktivt och kan därför användas.

## <a name="create-and-manage-product-readiness-policies"></a>Skapa och hantera principer för produktberedskap

Använd principer för produktberedskap när du vill hantera beredskapskontroller som gäller en produkt. Varje beredskapspolicy innehåller en uppsättning beredskapskontroller. När en beredskapspolicy tilldelas en teknisk produktkategori eller en delad produkt kommer alla produkter som är relaterade till den kategorin eller delade produkten ha beredskapskontroller som ingår i beredskapspolicyn.

För att arbeta med policyer för produktberedskap, gå till **Konstruktionsändringshantering \> Inställning \> Principer för produktberedskap**. Gör sedan något av följande.

- Om du vill skapa en ny policy väljer du **ny** i åtgärdsfönstret och anger sedan fälten enligt beskrivningen i följande underavsnitt.
- Om du vill redigera en befintlig policy markerar du den i listvyn, väljer **Redigera** i åtgärdsfönstret och anger sedan fälten enligt beskrivningen i följande underavsnitt.
- Om du vill ta bort en befintlig policy markerar du den i listfönstret och väljer du **Redigera** i åtgärdsfönstret och sedan på snabbfliken **Allmänt** ser du till att alternativet **Aktiv** anges till *Nej*. Välj sedan **Ta bort** i åtgärdsfönstret.

### <a name="header"></a>Siduvud

Ange följande fält i rubriken för en produktberedskapspolicy.

| Fält | beskrivning |
|---|---|
| Namn | Ange ett namn på policy. |
| beskrivning | Ange en beskrivning för policyn. |

### <a name="general-fasttab"></a>Snabbfliken Allmänt

Ange följande fält i snabbfliken **Allmänt** i en produktberedskapspolicy.

| Fält | beskrivning |
|---|---|
| Produkttyp | Välj om policyn gäller för produkter av typen *artikel* eller *tjänst*. Du kan inte ändra den här inställningen när du har sparat posten. |
| Aktiva | Använd det här alternativet för att upprätthålla dina beredskapsprinciper. Ange värdet *Ja* för alla beredskapsprinciper som du använder. Ställ in den på *Nej* för att markera att en beredskapsprincip är inaktiv när den inte används. Observera att du inte kan inaktivera en beredskapsprincip som är tilldelad en teknisk produktkategori eller en delad produkt, och du bara kan ta bort inaktiva frisläppningsprinciper. |

### <a name="readiness-control-fasttab"></a>Snabbfliken beredskapskontroll

För varje typ av beredskapskontroll som du vill inkludera i policyn, lägg till en rad på snabbfliken **beredskapskontroll**. Använd följande knappar i verktygsfältet snabbflik om du vill lägga till och ta bort rader som du behöver:

- **Lägg till kontroll** – Lägg till en standard beredskapskontroll till policyn. När du väljer den här knappen visas dialogrutan **Lägg till**. Där kan du välja från en lista med tillgängliga kontroller.
- **Lägg till befintlig enkät** – Lägg till en tom rad i rutnätet. Du kan sedan tilldela en befintlig enkät genom att konfigurera fälten i följande tabell.
- **Kopiera** – Lägg till en kopia av den markerade raden i rutnätet.
- **Ta bort** – ta bort den markerade raden från rutnätet.

Ange följande fält för varje rad du lägger till.

| Fält | beskrivning |
| --- | --- |
| Processområde | Markera området som kontrollen är relaterad till. |
| Typ | Välj om kontrollen är en systemkontroll, en manuell kontroll eller en kontrollista (enkät). |
| Namn | Om kontrollen är en kontrollista anger du ett namn. För system- och manuella kontroller ställs detta fält automatiskt in. |
| beskrivning | Om kontrollen är en kontrollista anger du en beskrivning. För system- och manuella kontroller ställs detta fält automatiskt in, och beskrivningen förklarar kontrollens fokus. |
| Tillämpa kontroller på | Välj om raden ska generera beredskapskontroller som svar på en ny frisläppt produkt, utgiven variant eller utgiven version. |
| Utför i | Välj om beredskapskontroller som raden genererar ska gälla för alla företag eller för ett enskilt företag. |
| Företag | Om du konfigurerar fältet **Köra i** till *Enskilt företag* väljer du företaget. |
| Ägartyp | Välj om beredskapskontroller som rad genereras ska tilldelas till en person eller ett team. |
| Ägare | Välj om beredskapskontroller som rad genereras ska tilldelas till en person eller ett team. |
| Enkät | Välj den enkät som ska användas för kontrollista. Check listan är en lokal kontrollista i företaget där beredskapskontrollen är klar. Systemet måste kunna bedöma om kontrollistan är korrekt besvarad. Därför måste kontrollistan ställas in så att en utvärdering görs baserat på korrekta svar. Mer information om hur du skapar enkäter finns i [Använda enkäter](/dynamicsax-2012/appuser-itpro/using-questionnaires) och dess tillhärande artiklar. |
| Automatiskt godkännande | Beredskapskontroll poster inkluderar en kryssruta **godkänd** som visar godkännandestatus. Markera kryssrutan **automatiskt godkännande** för kontroller som ska ställas in på godkänd omedelbart efter att den tilldelade användaren har slutfört dem. Avmarkera den här kryssrutan om du vill att explicit godkännande ska krävas som ett ytterligare steg. |
| Obligatoriskt | Markera den här kryssrutan för kontroller som måste slutföras av den tilldelade användaren. Obligatoriska kontroller kan inte hoppas över. |

<a name="assign-policy"></a>

## <a name="assign-readiness-policies-to-standard-and-engineering-products"></a>Tilldela en beredskapspolicy till standardprodukter och konstruktionprodukter

När du skapar en ny produkt baserad på en teknisk kategori, skapar du både en *frisläppt produkt* och en relaterad delad *produkt*. Hur beredskapspolicyer löses för en släppt produkt beror på om funktionen *Kontroller av produktberedskap* är aktiverad för ditt system (se avsnittet [Kontroller av beredskap för standardprodukter](#standard-products) senare i denna artikel för mer information om den här funktionen och hur du slår den på eller av).

- När funktionen *Produkt beredskapskontroller* är inaktiverad *av* på ditt system är beredskapspolicyn inställd och visas endast på poster [tekniska kategori](engineering-versions-product-category.md). För att lära sig vilken policy som gäller för en släppt produkt kontrollerar systemet fält **produktberedskapspolicy** för den relaterade ingenjörskategorin. Du kan ändra beredskapspolicyn för en befintlig produkt genom att redigera den relaterade tekniska kategorin (inte den delade produkten).
- När funktionen *Produkt beredskapskontroller* slås *på*, lägger det till ett fält för **Produktberedskapspolicy** till sidan **Produkt** page (där delade produkter ställs in) och till **Frisläppt produkt** (där värdet är skrivskyddat och hämtas från den relaterade delade produkten). Systemet hittar beredskapspolicyn för en frisläppt produkt genom att kontrollera den relaterade delade produkten. När du använder en teknisk kategori för att skapa en ny teknikprodukt skapas både en delad produkt och en frisläppt produkt av systemet och eventuella inställningar för **produktberedskapspolicy** för den tekniska kategorin kopieras till den nya delade produkten. Du kan ändra beredskapspolicyn för en befintlig produkt genom att redigera den relaterade delade produkten (inte den släppta ingenjörskategorin).

Följ dessa steg för att tilldela en beredskapspolicy till en delad produkt.

1. Gå till **Produktinformation \> Produkter \> Produkter**.
1. Öppna eller skapa en produkt som du vill tilldela en beredskapspolicy till.
1. På snabbfliken **Allmänt** ange fältet **Produktberedskapspolicy** till namnet på den policy som ska gälla för produkten.

Följ dessa steg för att tilldela en tekniska kategorin till en delad produkt.

1. Gå till **konstruktionsändringshantering \> inställning \> information om konstruktionsproduktkategori**.
1. Öppna eller skapa en tekniska kategori som du vill tilldela en beredskapspolicy till.
1. På snabbfliken **Produktberedskapspolicy** ange fältet **Produktberedskapspolicy** till namnet på den policy som ska gälla för den tekniska kategorin.

<a name="standard-products"></a>

## <a name="readiness-checks-on-standard-products"></a>Kontroller av beredskap för standardprodukter

Du kan aktivera kontroller i produktberedskap för standardprodukter (icke-konstruktion) genom att aktivera funktionen *Produkt beredskapskontroller* i funktionshanteringen. Den här funktionen gör några små ändringar i beredskapskontrollsystemet så att den stöder standardprodukter.

### <a name="enable-or-disable-readiness-checks-on-standard-products"></a>Aktivera eller inaktivera beredskapskontroller av standardprodukter

Den här funktionen kräver att både kontrollfunktionerna för *Konstruktionsändringshantering* och *Kontroller av produktberedskap* är aktiverad för systemet. Information om hur du aktiverar och inaktiverar funktionerna finns i [Översikt över hantering av tekniska ändringar](product-engineering-overview.md).

### <a name="create-readiness-policies-for-standard-products"></a>Skapa en beredskapspolicy för standardprodukter

Du skapar en beredskapspolicy för standardprodukter på samma sätt som för tekniska produkter. Se informationen tidigare i denna artikel.

### <a name="assign-readiness-policies-to-standard-products"></a>Tilldela beredskapspolicy för standardprodukter

Om du vill tilldela en beredskapspolicy till en standardprodukt öppnar du den relaterade delade produkten och konfigurerar fältet för **Produktberedskapspolicy** på namnet för den policy som ska användas. Mer information finns i avsnittet [Tilldela beredskapspolicyer för standardprodukter och tekniska produkter](#assign-policy) tidigare i denna artikel.

### <a name="view-and-process-readiness-checks-on-standard-products"></a>Visa och behandla beredskapskontroller av standardprodukter

När den här funktionen aktiveras kan du visa och bearbeta beredskapskontroller för standardprodukter på samma sätt som för tekniska produkter. Se informationen tidigare i denna artikel.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
