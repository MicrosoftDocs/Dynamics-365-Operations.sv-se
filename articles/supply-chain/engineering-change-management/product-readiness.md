---
title: Produktberedskap
description: I det här avsnittet beskrivs hur du kan använda beredskapskontroller för att säkerställa att nödvändiga huvuddata har slutförts för en produkt innan de används i transaktioner.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 8321a0d8516a6c2c085ce9c1236f70af1cca98da
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967268"
---
# <a name="product-readiness"></a>Produktberedskap

[!include [banner](../includes/banner.md)]

Du kan använda beredskapskontroller för att säkerställa att alla nödvändiga huvuddata har specificerats för en produkt innan de används i transaktioner. När beredskapskontroller används blir en användare eller ett team ansvarigt för att validera specifika fördefinierade produktspecifika data. Om det finns en öppen beredskapskontroll för en produkt kan produkten inte frisläppas eller användas i transaktioner.

Kryssrutan **Aktiv** för en teknisk produkt, variant eller version är endast tillgänglig efter att alla nödvändiga data har angetts och verifierats och efter att alla beredskapskontroller har bearbetats. Vid den tidpunkten kan produkten, versionen eller varianten frisläppas till andra företag och användas i transaktioner. Du kan skapa beredskapskontroller för nya produkter, nya varianter och nya konstruktionsversioner.

## <a name="types-of-readiness-checks"></a>Typer av beredskapskontroller

Det finns tre typer av beredskapskontroller:

- **Systemkontroll** – systemet kontrollerar om det finns en giltig post. Posten kan till exempel vara en aktiv strukturlista.
- **Manuell kontroll** – en användare verifierar om posten är giltig. En beredskapskontroll kan till exempel kräva validering av standard orderinställningarna. I vissa fall, t.ex. när produkten fortfarande är konstruerad och därför inte kommer att placeras i lager, krävs inga standard orderinställningar. Standard orderinställningar kan dock krävas för en annan produkt av samma typ, eftersom produkten kan hållas i lager. Användaren är ansvarig för att veta hur man korrekt fattar beslut om en beredskapskontroll krävs.
- **Kontrollista** – användaren svarar på en serie frågor från en kontrollista och systemet avgör om svaren möter förväntningarna. Kontrollistan kan ha vilket ämne som helst. Det kan till exempel användas för att avgöra om marknadsföringsmaterial eller produktdokumentation är slutförd.

## <a name="how-readiness-checks-are-created-for-a-new-product-variant-or-version"></a>Hur beredskapskontroller skapas för en ny produkt, variant eller version

När du skapar en ny teknisk **produkt** fastställer systemet om en policy för beredskapskontroll har ställts in för den tekniska produktkategorin. (Policyer för beredskapskontroll kan användas på den frisläppta produktnivån, den släppta variantnivån och teknisk versionsnivån). Om en princip har ställts in inträffar följande händelser:

- Beredskapskontroller skapas för produkten enligt tillämplig policy.
- Tekniska versionen är inaktiverad för att blockera produkten från att användas. Alla versioner för den specifika produkten som ingår är inställda på inaktiv.

Om en ny **variant** skapas för en produkt kontrollerar systemet om beredskapskontrollerna har ställts in för teknisk produktkategori. (Beredskapskontroller kan användas på den frisläppta variantnivån och teknisk versionsnivån). Om en beredskapskontroll har ställts in inträffar följande händelser:

- Beredskapskontroller skapas för produkten.
- Tekniska versionen är inaktiverad för att blockera produkten från att användas.

Om en ny teknisk **version** skapas för en produkt kontrollerar systemet om beredskapskontrollerna har ställts in för teknisk produktkategori. (Beredskapskontroller kan användas på teknisk versionsnivån). Om en beredskapskontroll har ställts in inträffar följande händelser:

- Beredskapskontroller skapas för produkten.
- Tekniska versionen är inaktiverad för att blockera produkten från att användas.

## <a name="view-readiness-checks"></a>Visa beredskapskontroller

### <a name="view-open-readiness-checks-for-a-product-or-product-version"></a>Visa öppna beredskapskontroller för en produkt eller produktversion

Om du vill hitta de öppna beredskapskontrollerna för en produkt öppnar du sidan **information om frisläppta produkter**. I åtgärdsfönstret, på fliken **Produkt**, i gruppen **Beredskapskontroller**, markerar du sedan **Beredskapskontroller**.

Om du vill hitta de öppna beredskapskontrollerna för en produktversion öppnar du sidan **tekniska versioner** för en frisläppt produkt och väljer en version. I åtgärdsfönstret, på fliken **Produkt**, i gruppen **Kontrollista**, markerar du sedan **Beredskapskontroller**.

### <a name="view-open-readiness-checks-that-are-assigned-to-you"></a>Visa öppna beredskapskontroller som har tilldelats dig

Följ de här stegen om du vill visa de öppna beredskapskontroller som har tilldelats dig.

- Gå till **Konstruktionsändringshantering \> Gemensamt \> Produktberedskap \> Mina öppna beredskapskontroller**.
- Gå till **Produktinformationshantering \> Arbetsytor \> Produktberedskap för diskret tillverkning**.

Den inställning som anger vem en beredskapskontroll är tilldelad för den konstruktionsproduktkategori. Beredskapskontroller kan tilldelas en person eller ett team. Om en beredskapskontroll tilldelas till ett team finns det en person i teamet som måste bearbeta beredskapskontrollen. För mer information, se [Konstruktionsversioner och kategorier av konstruktionsprodukter](engineering-versions-product-category.md).

## <a name="process-open-readiness-checks"></a>Bearbeta öppna beredskapskontroller

### <a name="process-system-and-manual-readiness-checks"></a>Bearbeta system- och manuella beredskapskontroller

När du har öppnat **beredskapskontroller** du kan visa ämnet för system- och manuella beredskapskontroller genom att välja **Visa relaterad information** i åtgärdsfönstret. Du kan sedan slutföra och/eller validera data för beredskapskontrollen. Öppna beredskapskontroller har **status** värdet *väntar*. Denna status anger att beredskapskontrollen fortfarande måste bearbetas. Följ ett av dessa steg för att bearbeta en beredskapskontroll.

- I åtgärdsfönstret, välj **kontrollera/slutföra** för att granska och slutföra beredskapskontrollen. När du är klar uppdateras fältet **Status** till *Godkänd*.
- Välj hoppa över i åtgärdsfönstret, välj **Hoppa över** om du vill hoppa över en beredskapskontroll som inte är obligatorisk. Du kan till exempel ställa in en beredskapskontroll för prisberäkningar. Du väljer dock att hoppa över den här kontrollen medan produkten fortfarande är i designfasen. I det här fallet uppdateras fältet **Status** till *Överhoppad*.

Beroende på konfigurationen av beredskapsprincipen, när fältet **Status** för beredskapskontroll har uppdaterats till *godkänd*, ett extra steg kan krävas för att godkänna beredskapskontrollen. I det här fallet väljer du **godkännande** för att slutföra beredskapskontrollen. Det här godkännandesteget är alltid obligatoriskt när beredskapskontrollen hoppas över.

När alla öppna beredskapskontroller för en ny produkt, variant eller version har bearbetats och godkänts efter behov, blir objektet automatiskt aktivt och kan därför användas.

### <a name="process-checklist-readiness-checks"></a>Bearbeta checklista beredskapskontroller

Öppna en checklista genom att öppna sidan **beredskapskontroller** och sedan välja **Starta checklista** i åtgärdsfönstret. När du har slutfört checklistan validerar systemet om beredskapskontrollen har passerats, baserat på inställningarna i enkäten. Om checken överförs uppdateras fältet **Status** uppdateras till *Godkänd*. Om beredskapskontrollen inte är obligatorisk kan du hoppa över den. I det här fallet uppdateras fältet **Status** till *Överhoppad*.

Beroende på konfigurationen av beredskapsprincipen, när fältet **Status** för beredskapskontroll har uppdaterats till *godkänd*, ett extra steg kan krävas för att godkänna beredskapskontrollen. I det här fallet väljer du **godkännande** för att slutföra beredskapskontrollen. Det här godkännandesteget är alltid obligatoriskt när beredskapskontrollen hoppas över.

När alla öppna beredskapskontroller för en ny produkt, variant eller version har bearbetats och godkänts efter behov, blir objektet automatiskt aktivt och kan därför användas.

## <a name="create-and-manage-product-readiness-policies"></a>Skapa och hantera principer för produktberedskap

Använd principer för produktberedskap när du vill hantera beredskapskontroller som gäller en produkt. Eftersom en beredskapspolicy tilldelas teknisk kategori gäller alla kontroller i beredskapspolicyn för alla teknik produkter som baseras på tekniska kategorin. För mer information, se [Konstruktionsversioner och kategorier av konstruktionsprodukter](engineering-versions-product-category.md).

Varje beredskapspolicy innehåller en uppsättning beredskapskontroller. När en beredskapspolicy tilldelas en teknisk produktkategori kommer alla produkter som skapas från den tekniska produktkategorin att ha beredskapskontroller som anges i beredskapspolicyn.

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
| Aktiva | Använd det här alternativet för att upprätthålla dina beredskapsprinciper. Ange värdet *Ja* för alla beredskapsprinciper som du använder. Ställ in den på *Nej* för att markera att en beredskapsprincip är inaktiv när den inte används. Observera att du inte kan inaktivera en beredskapsprincip som är tilldelad en teknisk produktkategori, och du bara kan ta bort inaktiva frisläppningsprinciper. |

### <a name="readiness-control-fasttab"></a>Snabbfliken beredskapskontroll

För varje typ av beredskapskontroll som du vill inkludera i policyn, lägg till en rad på snabbfliken **beredskapskontroll**. Använd följande knappar i verktygsfältet snabbflik om du vill lägga till och ta bort rader som du behöver:

- **Lägg till kontroll** – Lägg till en standard beredskapskontroll till policyn. När du väljer den här knappen visas dialogrutan **Lägg till**. Där kan du välja från en lista med tillgängliga kontroller.
- **Lägg till befintlig enkät** – Lägg till en tom rad i rutnätet. Du kan sedan tilldela en befintlig enkät genom att ställa in fälten i följande tabell.
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
| Företag | Om du ställer in fältet **Köra i** till *Enskilt företag* väljer du företaget. |
| Ägartyp | Välj om beredskapskontroller som rad genereras ska tilldelas till en person eller ett team. |
| Ägare | Välj om beredskapskontroller som rad genereras ska tilldelas till en person eller ett team. |
| Enkät | Välj den enkät som ska användas för kontrollista. Check listan är en lokal kontrollista i företaget där beredskapskontrollen är klar. Systemet måste kunna bedöma om kontrollistan är korrekt besvarad. Därför måste kontrollistan ställas in så att en utvärdering görs baserat på korrekta svar. Mer information om hur du skapar enkäter finns i [använda enkäter](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/using-questionnaires) och den närliggande informationen. |
| Automatiskt godkännande | Beredskapskontroll poster inkluderar en kryssruta **godkänd** som visar godkännandestatus. Markera kryssrutan **automatiskt godkännande** för kontroller som ska ställas in på godkänd omedelbart efter att den tilldelade användaren har slutfört dem. Avmarkera den här kryssrutan om du vill att explicit godkännande ska krävas som ett ytterligare steg. |
| Obligatoriskt | Markera den här kryssrutan för kontroller som måste slutföras av den tilldelade användaren. Obligatoriska kontroller kan inte hoppas över. |
