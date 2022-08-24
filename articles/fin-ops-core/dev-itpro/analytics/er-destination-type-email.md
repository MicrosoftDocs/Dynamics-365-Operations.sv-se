---
title: ER-målstyp för e-post
description: I den här artikeln beskrivs hur du konfigurerar en e-post-destination för varje MAPP- eller FIL-komponent i ett elektroniskt rapporteringsformat (ER).
author: kfend
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 97423
ms.assetid: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
ms.openlocfilehash: 5e58618618d9125db4c81f49f62f48c2ce2f5e62
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285438"
---
# <a name="email-er-destination-type"></a>ER-målstyp för e-post

[!include [banner](../includes/banner.md)]

När ett elektroniskt rapporteringsformat (ER) körs kan ett eller flera utgående dokument genereras. **Mapp**- eller **Fil**-formatkomponenter används i ER-format för att specificera strukturen för utgående dokument. Du kan konfigurera ett e-postmål för dessa typer av komponenter så att utgående dokument skickas som e-postbilagor.

Du kan konfigurera ett e-postmål för varje **Mapp**- eller **Fil**-komponent i ett ER-format. I det här fallet **e-postas varje utgående dokument separat**. Baserat på denna målinställning levereras ett genererat dokument som en bilaga till ett e-postmeddelande. 

> [!NOTE]
> Om inget dokument genereras på grund av att uttrycket **Aktiverad** för den relevanta **Fil**-komponenten har konfigurerats att returnera **Falskt** booleskt värde skickas inget e-postmeddelande, även om e-postmål har konfigurerats och aktiverats för komponenten.

Du kan också [gruppera](#grouping) flera **mapp**- eller **fil**-komponenter samtidigt och sedan konfigurera ett e-postmål för alla komponenter i gruppen. I det här fallet skickas alla utgående dokument som genereras av komponenter som tillhör gruppen **som flera bilagor till ett enda e-postmeddelande**. Baserat på denna målinställning levereras varje genererat dokument som en bilaga till ett separat e-postmeddelande.

> [!NOTE]
> Om minst ett dokument genereras av en **fil**-komponent i en grupp komponenter, skickas ett e-postmeddelande. Om inget dokument genereras av grupperade komponenter på grund av att uttrycket **Aktiverad** för varje **Fil**-komponent har konfigurerats att returnera **Falskt** booleskt värde skickas inget e-postmeddelande, även om e-postmål har konfigurerats och aktiverats för den gruppen komponenter.
>
> **E-post** är den enda destination som kan konfigureras för en grupp komponenter. För att leverera ett dokument som har e-postats baserat på inställningen för e-postdestination för en grupp, lägger du till ytterligare en destinationspost, väljer önskad komponent och konfigurerar sedan ytterligare en destination för posten.

Flera grupper av komponenter kan konfigureras för en enda ER-formatkonfiguration. På det här sättet kan du konfigurera ett e-postmål för varje grupp komponenter och ett e-postmål för varje komponent.

## <a name="enable-an-email-destination"></a>Aktivera e-postmål

Följ de här stegen om du vill skicka en eller flera utdatafiler med e-post.

1. På sidan **Elektronisk rapporteringsdestination** på snabbfliken **Fildestination**, välj en komponent eller grupp av komponenter i rutnätet.
2. Välj **Inställningar** och sedan i dialogrutan **Målinställningar** på fliken **E-post** ange alternativet **Aktiverad** till **Ja**.

[![Ange alternativet för Aktivera som Ja för ett e-postmål.](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)

## <a name="configure-an-email-destination"></a>Konfigurera en e-postdestination

### <a name="email-content"></a>E-postinnehåll

Du kan redigera ämnet och brödtexten i e-postmeddelandet.

I fältet **Ämne** anger du texten i e-postmeddelandets ämne som ska visas i ämnesfältet för ett elektroniskt meddelande som genereras i samband med körning. I fältet **Brödtext** anger du texten i e-postmeddelandets brödtext som ska visas i brödtextfältet för ett elektroniskt meddelande. Du kan skapa konstanta texter för e-postmeddelandets rubrik och brödtext, eller också använda ER-[formler](er-formula-language.md) för att skapa e-posttexter dynamiskt i samband med körning. Den konfigurerade formeln måste returnera ett värde av typen [Sträng](er-formula-supported-data-types-primitive.md#string).

E-postmeddelandets brödtext består av text- eller HTML-format, beroende på e-postklient. Du kan använda alla layouter, format och märken som HTML och infogade övergripande formatmallar (CSS) tillåter.

> [!NOTE]
> E-postklienterna har begränsningar för layout och stil som kan kräva justeringar av HTML-koden och den CSS som du använder för meddelandetexten. Vi rekommenderar att du bekantar dig med de bästa metoderna för att skapa HTML-kod som stöds av de vanligaste e-postklienterna.
>
> Använd rätt kodning när du vill implementera en transportretur, beroende på brödtextformatering. Mer information finns i definitionen för datatypen [Sträng](er-formula-supported-data-types-primitive.md#string).

### <a name="email-addresses"></a>E-postadresser

Du kan ange avsändare och mottagare för e-post. Som standard skickas e-postmeddelanden på uppdrag av den aktuella användaren. Om du vill ange en annan e-postavsändare måste du konfigurera fältet **Från**.

> [!NOTE]
> När en e-postdestination är konfigurerad visas fältet **Från** endast för användare som har säkerhetsbehörighet `ERFormatDestinationSenderEmailConfigure`, **Konfigurera avsändarens e -postadress för destinationer i ER-format**.
>
> När en e -postdestination erbjuds för ändring [körtid](electronic-reporting-destinations.md#security-considerations), visas endast fältet **Från** för användare som har `ERFormatDestinationSenderEmailMaintain` säkerhetsbehörighet, **Behåll avsändarens e -postadress för ER -formatmålet**.
>
> När fältet **Från** är konfigurerat för att använda en annan e-postadress än den nuvarande användarens, antingen behörigheten **Skicka som** eller **Skicka på uppdrag för** måste vara korrekt [ange](/microsoft-365/solutions/allow-members-to-send-as-or-send-on-behalf-of-group) i förväg. Annars kastas följande undantag vid körning: "Det går inte att skicka e -post som \<from email account\> från \<current user account\> kontot, kontrollera "Skicka som"-behörigheten på \<from email account\>."

Du kan konfigurera fältet **Från** för att returnera mer än en e -postadress. I det här fallet används den första adressen i listan som avsändaradress i e-post.

Om du vill ange e-postmottagare måste du konfigurera fälten **Till** och **Kopia** (valfritt).

Du kan konfigurera e-postadresser för ER på två sätt. Konfigurationen kan slutföras på samma sätt som funktionen utskriftshanterings, eller så kan du lösa en e-postadress genom att använda en direkt referens till ER-konfigurationen via en formel.

## <a name="email-address-types"></a>E-postadresstyper

Om du väljer fält **Redigera** bredvid **Från**, **Till** eller **Kopia** i dialogrutan **Målinställningar** visas enbart dialogrutan **E-post från**, **E-post till** eller **E-post kopia** visas. Där kan du konfigurera avsändare och e-postmottagare. Välj **Lägg till** och välj sedan vilken typ av e-postadress som ska användas. Två typer stöd för närvarande: **Utskriftshanterings-e-post** och **Konfigurations-e-postmeddelande**.

[![Välja typ av e-postadress.](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)

### <a name="print-management-email"></a>E-postmeddelande om utskriftshantering

Om du väljer **Utskriftshanterings-e-post** som e -postadresstyp kan du ange fasta e -postadresser i dialogrutan **E-post från**, **E-post till** eller **E-post kopia** genom att ställa in följande fält:

- I fältet **E-postkälla** väljer du **Ingen**.
- I fältet **Ytterligare e-postadresser, åtskilda av ";"** anger du de fasta e-postadresserna.

Du kan också få e-postadresser från kontaktinformationen för den part som du genererar ett utgående dokument för. För att använda e-postadresser som inte är fast väljer du, i fältet **E-postkälla**, [rollen](../../fin-ops/organization-administration/overview-global-address-book.md#party-roles) för parten för fildestinationen. Följande roller stöds:

- Kund
- Leverantör
- Potentiell kund
- Kontakt
- Konkurrent
- Arbetare
- Sökande
- Potentiell leverantör
- Otillåten leverantör
- Juridisk person

Om du till exempel vill konfigurera ett e-postmål för ett ER-format som används för att bearbeta leverantörsbetalningar, väljer du rollen **Leverantör**.

När du har valt önskad roll väljer du knappen **Bind** (kedjesymbolen) bredvid fältet **E-postkällkonto** för att öppna [formeldesigner](general-electronic-reporting-formula-designer.md). Du kan sedan använda sidan för att konfigurera en formel som , under körningen, returnerar konto numret för den part som tilldelats den konfigurerade rollen från det bearbetade dokumentet till e-postdestinationen.

> [!NOTE]
> Formlerna är specifika för ER-konfigurationen.

På sidan **Formeldesigner** anger du i fältet **Formel** en dokumentspecifik referens till en roll som stöds. I stället för att skriva referensen i fönstret **Datakälla** letar du upp och markerar datakällnoden som representerar ett konto för den konfigurerade rollen och väljer sedan **Lägg till datakälla** för att uppdatera formeln. Om du till exempel konfigurerar e-postdestinationen för konfigurationen **ISO 20022-kreditöverföring** som används för att bearbeta leverantörsbetalningar är noden som representerar ett leverantörskonto `'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.

![Konfigurera ett e-postkällkonto.](./media/er_destinations-emaildefineaddresssource.gif)

Om kontonumren för den konfigurerade rollen är unika för hela instansen av Microsoft Dynamics 365 Finance kan fältet **Företag för e-postkälla** i dialogrutan **E-post till** vara tomt.

Alternativt kan du ha en situation där olika parter i den [globala adressboken](../../fin-ops/organization-administration/overview-global-address-book.md) har registrerats i olika företag ([juridiska personer](../../fin-ops/organization-administration/organizations-organizational-hierarchies.md#legal-entities)) på ett sådant sätt att alla använder samma kontonummer för den konfigurerade rollen. I det här fallet är kontonumren för den konfigurerade rollen inte unika för hela ekonomiinstansen. Du kan därför inte uttryckligen välja en part genom bara ange ett kontonummer. Du måste också ange företaget som parten har registrerats i omfattningen för att fylla den konfigurerade rollen. Välj du knappen **Bind** (kedjesymbolen) bredvid fältet **Företag för e-postkälla** i dialogrutan **E-post till** för att öppna [formeldesignern](general-electronic-reporting-formula-designer.md). Du kan sedan använda den här sidan för att konfigurera en formel som, under körning, returnerar koden för det företag som den önskade källan kan hittas i omfattningen för.

> [!TIP]
> Om du måste använda företagskoden för att köra ett ER-format, men ER-formatet inte innehåller någon datakälla som företagskoden kan hämtas från, konfigurerar du konfigurerar du formeln `GetCurrentCompany()` med hjälp av den inbyggda ER-funktionen [GETCURRENTCOMPANY](er-functions-other-getcurrentcompany.md).

> [!NOTE]
> Formlerna är specifika för ER-konfigurationen.

Om du vill ange vilken typ av e-postadresser som ska användas vid körning väljer du **Redigera** bredvid fältet **Till** i dialogrutan **E-post till** för att öppna listrutedialogen **Tilldela e-postadress**. Ange sedan följande fält:

- I fältet **Syfte** väljer du önskade syften. Endast e-postadresser för de valda syftena från kontakter från den identifierade parten kommer att användas.
- Ställ in alternativet **Primär kontakt** som **Ja** för att använda en e-postadress som konfigurerats för den identifierade parten som primär e-postadress.

> [!NOTE]
> Om syften väljs i fältet **Syfte** och alternativet **Primär kontakt** samtidigt är inställt på **Ja** kommer all e-post som uppfyller minst ett konfigurerat kriterium att användas vid körning.

### <a name="configuration-email"></a>Konfigurations-e-postmeddelande

Välj **Konfigurations-e-post** som e-postadresstyp om konfigurationen som du använder har en nod i datakällorna som returnerar antingen en enskild e-postadress eller flera e-postadresser som avgränsas med semikolon (;). Du kan använda datakällor och [funktioner](er-formula-language.md#Functions) i formeldesignern för att få en korrekt formaterad e-postadress eller korrekt formaterade e-postadresser som avgränsas med semikolon. Om du till exempel använder en konfiguration för **ISO 20022 kreditöverföring** representerar noden den primära e-postadressen för en leverantör från leverantörens kontaktuppgifter som följebrevet ska skickas till är `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.

[![Konfigurera en e-postadresskälla.](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)

## <a name="group-format-components"></a><a id="grouping"></a>Gruppera formatkomponenter

För att gruppera formatkomponenter på sidan **Elektronisk rapporteringsdestination** väljer du på FastTab för **Fildestination** komponenterna i rutnätet och väljer sedan **Gruppera**.

**E-postadressen** är den enda tidigare konfigurerade destinationen som fortfarande är tillgänglig för de valda komponenterna. Inga andra tidigare konfigurerade destinationer är tillgängliga eftersom de betraktas ej ha stöd för en grupp komponenter. Du meddelas om dessa ändringar efter behov.

Posten som du har tidigare lagt till betraktas som rubrik för den grupp som skapas. Den här rubrikposten innehåller gruppens inställningar för e-postdestination. Andra poster är gruppmedlemmar som kommer att använda e-postdestinationsinställningarna för gruppens rubrikpost.

Om du vill dela upp formatkomponenter väljer du på FastTab för **Fildestination** en post som tillhör gruppen och väljer sedan **Dela upp grupp**.

- Om du väljer en rubrikpost delas hela gruppen upp.
- Om du väljer en medlemspost och det är den sista medlemsposten i en grupp, kommer hela gruppen att delas upp.
- Om du väljer en medlemspost som inte är den sista medlemsposten i en grupp, kommer den posten att exkluderas från den aktuella gruppen.

Följande bild visar strukturen för ett ER-format som har konfigurerats för att producera en zippad utgående fil som innehåller en kravbrevsfaktura och lämpliga kundfakturor i PDF-format.

[![Struktur för ett ER-format som genererar utgående dokument.](./media/ER_Destinations-Email-Grouping1.png)](./media/ER_Destinations-Email-Grouping1.png)

Följande illustration visar processen, som beskrivs i det här ämnet, för gruppering av enskilda komponenter och aktivering av **e-postdestinationen** för den nya gruppen, så att en kravbrevsfaktura skickas tillsammans med lämpliga kundfakturor som e-postbilagor.

[![Gruppera enskilda komponenter och aktivera e-postdestinationen.](./media/ER_Destinations-Email-Grouping2.gif)](./media/ER_Destinations-Email-Grouping2.gif)

## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)
- [Destinationer för elektronisk rapportering (ER)](electronic-reporting-destinations.md)
- [Formeldesigner i elektronisk rapportering (ER)](general-electronic-reporting-formula-designer.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
