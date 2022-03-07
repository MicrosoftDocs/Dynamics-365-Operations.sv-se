---
title: Skapa ER-uttryck för att anropa programklassmetoder
description: Det här ämnet beskriver hur du återanvänder befintlig programlogik i konfigurationer för elektronisk rapportering genom att anropa metoder för programklasser i ER-uttryck.
author: NickSelin
ms.date: 11/02/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 81fae8d3603677afd7dd4b09b9073805f73582b4
ms.sourcegitcommit: e6b4844a71fbb9faa826852196197c65c5a0396f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/04/2021
ms.locfileid: "7751716"
---
# <a name="design-er-expressions-to-call-application-class-methods"></a>Skapa ER-uttryck för att anropa programklassmetoder

[!include [banner](../../includes/banner.md)]

Detta ämne beskriver hur du återanvänder befintlig programlogik i konfigurationer för [elektronisk rapportering (ER)](../general-electronic-reporting.md) genom att anropa erforderliga metoder för programklasser i ER-uttryck. Värden på argument för att anropa klasser kan definieras dynamiskt vid körning. Värden kan till exempel baseras på information i parsingdokumentet för att säkerställa att detta är korrekt.

För exemplet i detta ämne ska du utforma en process som parsar inkommande bankutdrag för en uppdatering av programdata. Du erhåller inkommande bankutdrag som textfiler (.txt) som innehåller IBAN-koder (International Bank Account Number). Som en del av processen för import av bankutdrag måste du bekräfta riktigheten i IBAN-koden med hjälp av befintlig logik.

## <a name="prerequisites"></a>Förutsättningar

Procedurerna i detta ämne är avsedda för användare som har tilldelats rollen som **Systemadministratör** eller **Elektronisk rapporteringsutvecklare**.

Procedurerna kan slutföras med hjälp av valfri datauppsättning.

Om du vill slutföra dem måste du ladda ned och spara följande fil: [SampleIncomingMessage.txt](https://download.microsoft.com/download/8/0/a/80adbc89-f23c-46d9-9241-e0f19125c04b/SampleIncomingMessage.txt).

I detta ämne ska du skapa erforderliga ER-konfigurationer för exempelföretaget Litware, Inc. Innan du slutför procedurerna i detta ämne måste du därför följa dessa steg.

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **Lokaliseringskonfigurationer** bekräftar du att konfigurationsleverantören för exempelföretaget **Litware, Inc.** är tillgängligt och har markerats som aktivt. Om du inte kan se denna konfigurationsleverantör måste du först slutföra stegen i [Skapa konfigurationsleverantörer och markera dem som aktiva](er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-a-new-er-model-configuration"></a>Importera en ny konfiguration för ER-modell

1. På sidan **Lokaliseringskonfigurationer**, i avsnittet **Konfigurationsleverantörer**, väljer du fönstret för konfigurationsleverantören **Microsoft**.
2. Välj **Databaser**.
3. På sidan **Lokaliseringsdatabaser** väljer du **Visa filter**.
4. Om du vill välja den globala databasposten lägger du till ett filterfält för **Namn**.
5. I fältet **Namn** anger du **Global**. Markera sedan filteroperatorn **innehåller**.
6. Välj **Tillämpa**.
7. Välj **[Öppna](../er-download-configurations-global-repo.md#open-configurations-repository)** för att granska listan över ER-konfigurationer i vald databas.
8. På sidan **Konfigurationsdatabas** i konfigurationsträdet väljer du **Betalningsmodell**.
9. I snabbfliken **Versioner**, om knappen **Importera** är tillgänglig, väljer du den och sedan **Ja**.

    Om knappen **Importera** inte är tillgänglig har du redan importerat vald version av ER-konfigurationen för **Betalningsmodell**.

10. Stäng sidan **Konfigurationsdatabas** och stäng sedan ner sidan **Lokaliseringsdatabaser**.

## <a name="add-a-new-er-format-configuration"></a>Lägg till en ny konfiguration för ER-format

Lägg till ett nytt ER-format som du vill dela upp inkommande bankutdrag i TXT-format.

1. På sidan **Lokaliseringskonfigurationer** väljer du fönstret **Rapporteringskonfigurationer**.
2. På sidan **Konfigurationer** i konfigurationsträdet i vänster panel, väljer du **Betalningsmodell**.
3. Välj **Skapa konfiguration**. 
4. Gör följande i listrutan:

    1. I fältet **Nytt** anger du **Format som baseras på datamodellen PaymentModel**.
    2. I fältet **Namn** anger du **Importformat för bankutdrag (exempel)**.
    3. I fältet **Stöder dataimport** väljer du **Ja**.
    4. Välj **Skapa konfiguration** för att slutföra skapandet av konfigurationen.

## <a name="design-the-er-format-configuration--format"></a>Designa konfiguration för ER-format – Format

Designa ett ER-format som representerar den externa filens förväntade struktur i TXT-format.

1. För den formatkonfiguration för **Importformat för bankutdrag (exempel)** som du har lagt till väljer du **Designer**.
2. På sidan **Formatdesigner**, i formatstrukturen i det vänstra fönstret, väljer du **Lägg till rot**.
3. Gör följande i dialogrutan som visas:

    1. I trädet väljer du **Text\\Sekvens** om du vill lägga till en formatkomponent för **Sekvens**.
    2. I fältet **Namn** anger du **Rot**.
    3. I fältet **Specialtecken** väljer du **Ny rad – Windows (CR LF)**. Utifrån den här inställningen beaktas varje rad i parsingfilen som en separat post.
    4. Välj **OK**.

4. Markera **Lägg till**.
5. Gör följande i dialogrutan som visas:

    1. I trädet väljer du **Text\\Sekvens**.
    2. I fältet **Namn** anger du **Rader**.
    3. Välj **Ett många** i fältet **Sammansatt**. Baserat på denna inställning förväntas minst en rad finnas med i parsningfilen.
    4. Välj **OK**.

6. I trädet väljer du **Rot\\Rader** och sedan **Lägg till sekvens**.
7. Gör följande i dialogrutan som visas:

    1. I fältet **Namn** anger du **Fält**.
    2. I fältet **Sammansatt** väljer du **Exakt ett**.
    3. Välj **OK**.

8. I trädet väljer du **Rot\\Rader\\Fält** och sedan **Lägg till**.
9. Gör följande i dialogrutan som visas:

    1. I trädet väljer du **Text\\Sträng**.
    2. I fältet **Namn** anger du **IBAN**.
    3.. Välj **OK**.

10. Välj **Spara**.

Konfigurationen har nu ställts in så att varje enskild rad i parsningfilen endast innehåller IBAN-koden.

![Formatkonfiguration för importformat för bankutdrag (exempel) på sidan Formatdesigner.](../media/design-expressions-app-class-er-01.png)

## <a name="design-the-er-format-configuration--mapping-to-a-data-model"></a>Designa ER-formatkonfigurationen – mappa till en datamodell

Designa en ER-formatmappning där information från parsingfilen används för att fylla i en datamodell.

1. På sidan **Formatdesigner** väljer du **Mappa format till model** i åtgärdsfönstret.
2. På sidan **Modell för mappning av datakälla** väljer du **Ny** i åtgärdsfönstret.
3. I fältet **Definition** väljer du **BankToCustomerDebitCreditNotificationInitiation**.
4. I fältet **Namn** anger du **Mappning till datamodell**.
5. Välj **Spara**.
6. Välj **Designer**.
7. På sidan **Modellmappingsdesigner**, i trädet **Datakälltyper**, väljer du **Dynamics 365 for Operations\\Klass**.
8. I avsnittet **Datakällor** väljer du **Lägg till rot** för att lägga till en datakälla som anropar befintlig programlogik för validering av IBAN-koder.
9. Gör följande i dialogrutan som visas:

    1. I fältet **Namn** anger du **Kontrollera\_koder**.
    2. I fältet **Klass** anger eller väljer du **ISO7064**.
    3. Välj **OK**.

10. I fältet **Typer av datakälla** följer du dessa steg:

    1. Expandera datakällan för **format**.
    2. Visa **format\\Root: Sequence(Root)**.
    3. Visa **format\\Root: Sequence(Root)\\Rows: Sequence 1..\* (rader)**.
    4. Visa **format\\Root: Sequence(Root)\\Rows: Sequence 1..\* (rader)\\Fields: Sequence 1..1 (fält)**.

11. I trädet **Datamodell** följer du dessa steg:

    1. Visa fältet **Betalningar** för datamodellen.
    2. Visa **Betalningar\\Fordringsägarkonto(CreditorAccount)**.
    3. Visa **Betalningar\\Fordringsägarkonto(CreditorAccount)\\Identifiering**.
    4. Visa **Betalningar\\Fordringsägarkonto(CreditorAccount)\\Identifiering\\IBAN**.

12. Följ dessa steg när du vill binda komponenter för konfigurerat format till datamodellfält:

    1. Välj **format\\Root: Sequence(Root)\\Rows: Sequence 1..\* (rader)**.
    2. Välj **Betalningar**.
    3. Välj **bind**. Utifrån den här inställningen beaktas varje rad i parsingfilen som en enskild betalning.
    4. Välj **format\\Root: Sequence(Root)\\Rows: Sequence 1..\* (rader)\\Fields: Sequence 1..1 (fält)\\IBAN: sträng(IBAN)**.
    5. Välj **Betalningar\\Fordringsägarkonto(CreditorAccount)\\Identifiering\\IBAN**.
    6. Välj **bind**. Baserat på den här inställningen fylls fältet **IBAN** i datamodellen i med värdet från parsingfilen.

    ![Bindande av formatkomponenter till datamodellfält på sidan Modellmappningsdesigner.](../media/design-expressions-app-class-er-02.png)

13. På fliken **Valideringar** följer du dessa steg för att lägga till en regel för [validering](../general-electronic-reporting-formula-designer.md#Validation) som visar ett felmeddelande för samtliga rader i parsingfilen som innehåller en ogiltig IBAN-kod:

    1. Välj **Ny** och sedan **Redigera villkor**.
    2. På sidan **Formeldesigner**, i trädet **Datakälla**, visar du den datakälla för **Kontrollera\_koder** som representerar programklassen **ISO7064** för att visa klassens tillgängliga metoder.
    3. Välj **Kontrollera\_koder\\verifyMOD1271\_36**.
    4. Välj **Lägg till datakälla**.
    5. I fältet **Formel** anger du följande [uttryck](../general-electronic-reporting-formula-designer.md#Binding): **Kontrollera\_koder.verifyMOD1271\_36(format.Root.Rows.Fields.IBAN)**.
    6. Markera **Spara** och stäng sedan sidan.
    7. Välj **Redigera meddelande**.
    8. På sidan **Formeldesigner**, i fältet **Formel**, anger du **CONCATENATE("Ogiltig IBAN-kod hittades:&nbsp;", format.Root.Rows.Fields.IBAN)**.
    9. Markera **Spara** och stäng sedan sidan.

    Baserat på dessa inställningar kommer valideringsvillkoret att returnera *[FALSE](../er-formula-supported-data-types-primitive.md#boolean)* för alla ogiltiga IBAN-koder genom att anropa befintlig **verifyMOD1271\_36**-metod för programklass **ISO7064**. Observera att värdet för IBAN-koden definieras dynamiskt vid körning som argument för anropsmetod, baserat på innehållet i TXT-parsingfilen.

    ![Valideringsregel på sidan för modellmappningsdesigner.](../media/design-expressions-app-class-er-03.png)

14. Välj **Spara**.
15. Stäng sidan **Modellmappningsdesigner** och stäng sedan sidan **Modell för mappning av datakälla**.

## <a name="run-the-format-mapping"></a>Kör mappning av filformat

För testningsändamål kör du formatmappningen med hjälp av samm SampleIncomingMessage.txt-fil som du tidigare laddade ned. Genererade utdata kommer att inkludera data som importeras från den valda textfilen och överförs till anpassad datamodell när den verkliga importen sker.

1. Ppå sidan **Modell för mappning av datakälla** välkjer du **Kör**.
2. På sidan **Parametrar för elektronisk rapport** väljer du **Bläddra**, letar upp filen **SampleIncomingMessage.txt** som du tidigare laddade ned, och väljer denna.
3. Välj **OK**.
4. Notera att **Modell för mappning av datakälla** visar ett felmeddelande om en ogiltig IBAN-kod.

    ![Resultatet av att köra formatmappningne på sidan Modell för mappning av datakälla.](../media/design-expressions-app-class-er-04.png)

5. Granska utdata i XML-format, vilket representerar de data som har importerats från den valda filen och integrerats i datamodellen. Observera att endast tre rader i den importerade textfilen bearbetades utan fel. IBAN-koden på rad 4 är ogiltig och har hoppats över.

    ![XML-utmatning.](../media/design-expressions-app-class-er-05.png)

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
