---
title: ER-målstyp för e-post
description: Det här ämnet beskriver hur du konfigurerar en e-postdestination för varje MAPP- eller FIL-komponent i ett ER-format (elektronisk rapportering) som har konfigurerats för att generera utgående dokument.
author: NickSelin
manager: AnnBe
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: c6242ecb44a206aacc0e1b1b3c4f588eadd18882
ms.sourcegitcommit: 53174ed4e7cc4e1ba07cdfc39207e7296ef87c1f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/07/2020
ms.locfileid: "4690136"
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

## <a name="configure-an-email-destination"></a>Konfigurera en e-postdestination

För att skicka en utdatafil eller flera utdatafiler via e-post ska du välja sidan **Elektronisk rapportering och destination** på **fildestination** FastTab, välja en komponent eller en grupp av komponenter i rutnätet och sedan välja **inställningar**. I dialogrutan **Målinställningar** som visas på fliken **E-post** anger du alternativet för **Aktiverad** som **Ja**. Du kan sedan ange e-postmottagare samt redigera e-postmeddelandets ämne och brödtext. Du kan antingen skapa konstant text för e-postmeddelandets ämne eller använda [ER-formler](er-formula-language.md) för att skapa e-posttexter dynamiskt.

Du kan konfigurera e-postadresser för ER på två sätt. Konfigurationen kan slutföras på samma sätt som funktionen utskriftshanterings slutför den, eller så kan du lösa en e-postadress genom att använda en direkt referens till ER-konfigurationen via en formel.

[![Aktiverar alternativet Ja för ett e-postmål](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)

## <a name="email-address-types"></a>E-postadresstyper

Om du väljer **Redigera** bredvid fältet **Till** eller **Kopia** i dialogrutan **Målinställningar** visas enbart dialogrutan **E-post**. Välj **Lägg till** och välj sedan vilken typ av e-postadress som ska användas. Två typer stöd för närvarande: **Utskriftshanterings-e-post** och **Konfigurations-e-postmeddelande**.

[![Välja typ av e-postadress](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)

### <a name="print-management-email"></a>E-postmeddelande om utskriftshantering

Om du väljer **Utskriftshanterings-e-post** som e-postadresstyp kan du ange fasta e-postadresser i dialogrutan **E-post till** genom att ställa in följande fält:

- I fältet **E-postkälla** väljer du **Ingen**.
- I fältet **Ytterligare e-postadresser, åtskilda av ";"** anger du de fasta e-postadresserna.

![Konfigurera en fast e-postadress](./media/er_destinations-emailfixedaddress.png)

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

Om du till exempel vill konfigurera ett e-postmål för ett ER-format som används för att bearbeta leverantörsbetalningar, väljer du rollen **Leverantör**.

När du har valt önskad roll väljer du knappen **Bind** (kedjesymbolen) bredvid fältet **E-postkällkonto** för att öppna [formeldesigner](general-electronic-reporting-formula-designer.md). Du kan sedan använda sidan för att konfigurera en formel som , under körningen, returnerar konto numret för den part som tilldelats den konfigurerade rollen från det bearbetade dokumentet till e-postdestinationen.

> [!NOTE]
> Formlerna är specifika för ER-konfigurationen.

På sidan **Formeldesigner** anger du i fältet **Formel** en dokumentspecifik referens till en roll som stöds. I stället för att skriva referensen i fönstret **Datakälla** letar du upp och markerar datakällnoden som representerar ett konto för den konfigurerade rollen och väljer sedan **Lägg till datakälla** för att uppdatera formeln. Om du till exempel konfigurerar e-postdestinationen för konfigurationen **ISO 20022-kreditöverföring** som används för att bearbeta leverantörsbetalningar är noden som representerar ett leverantörskonto `'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.

![Konfigurera ett e-postkällkonto](./media/er_destinations-emaildefineaddresssource.gif)

Om kontonumren för den konfigurerade rollen är unika för hela instansen av Microsoft Dynamics 365 Finance kan fältet **Företag för e-postkälla** i dialogrutan **E-post till** vara tomt.

![Tomt fält Företag för e-postkälla](./media/er_destinations-emaildefineaddresssourceformula.png)

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

![Konfigurera ett attributkonto för e-postkälla](./media/er_destinations-emaildefineaddresssourceattributes.png)

### <a name="configuration-email"></a>Konfigurations-e-postmeddelande

Välj **Konfigurations-e-post** som e-postadresstyp om konfigurationen som du använder har en nod i datakällorna som returnerar antingen en enskild e-postadress eller flera e-postadresser som avgränsas med semikolon (;). Du kan använda [datakällor](general-electronic-reporting.md#FormatComponentOutbound) och [funktioner](er-formula-language.md#functions) i formeldesignern för att få en korrekt formaterad e-postadress eller korrekt formaterade e-postadresser som avgränsas med semikolon. Om du till exempel använder en konfiguration för **ISO 20022 kreditöverföring** representerar noden den primära e-postadressen för en leverantör från leverantörens kontaktuppgifter som följebrevet ska skickas till är `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.

[![Konfigurera ett e-postadresskonto](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)

## <a name="group-format-components"></a><a id="grouping"></a>Gruppera formatkomponenter

För att gruppera formatkomponenter på sidan **Elektronisk rapporteringsdestination** väljer du på FastTab för **Fildestination** komponenterna i rutnätet och väljer sedan **Gruppera**.

**E-postadressen** är den enda tidigare konfigurerade destinationen som fortfarande är tillgänglig för de valda komponenterna. Inga andra tidigare konfigurerade destinationer är tillgängliga eftersom de betraktas ej ha stöd för en grupp komponenter. Du meddelas om dessa ändringar efter behov.

Posten som du har tidigare lagt till betraktas som rubrik för den grupp som skapas. Den här rubrikposten innehåller gruppens inställningar för e-postdestination. Andra poster är gruppmedlemmar som kommer att använda e-postdestinationsinställningarna för gruppens rubrikpost.

Om du vill dela upp formatkomponenter väljer du på FastTab för **Fildestination** en post som tillhör gruppen och väljer sedan **Dela upp grupp**.

- Om du väljer en rubrikpost delas hela gruppen upp.
- Om du väljer en medlemspost och det är den sista medlemsposten i en grupp, kommer hela gruppen att delas upp.
- Om du väljer en medlemspost som inte är den sista medlemsposten i en grupp, kommer den posten att exkluderas från den aktuella gruppen.

Följande bild visar strukturen för ett ER-format som har konfigurerats för att producera en zippad utgående fil som innehåller en kravbrevsfaktura och lämpliga kundfakturor i PDF-format.

[![Struktur för ett ER-format som genererar utgående dokument](./media/ER_Destinations-Email-Grouping1.png)](./media/ER_Destinations-Email-Grouping1.png)

Följande illustration visar processen, som beskrivs i det här ämnet, för gruppering av enskilda komponenter och aktivering av **e-postdestinationen** för den nya gruppen, så att en kravbrevsfaktura skickas tillsammans med lämpliga kundfakturor som e-postbilagor.

[![Gruppera enskilda komponenter och aktivera e-postdestinationen](./media/ER_Destinations-Email-Grouping2.gif)](./media/ER_Destinations-Email-Grouping2.gif)

## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)
- [Destinationer för elektronisk rapportering (ER)](electronic-reporting-destinations.md)
- [Formeldesigner i elektronisk rapportering (ER)](general-electronic-reporting-formula-designer.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]