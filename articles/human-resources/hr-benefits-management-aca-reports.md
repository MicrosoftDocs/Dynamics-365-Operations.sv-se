---
title: Generera sjukförsäkringsrapporter i förmånshanteringen
description: I denna artikel beskrivs hur förmånshantering spårar information som rapporteras i formulär 1095-B och formulär 1095-C för arbetsgivarmandatet för sjukförsäkring (ACA).
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-12-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: d51e16345ab18904ebe55c1ec802446fc89d46d6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8889734"
---
# <a name="generate-aca-reports-in-benefits-management"></a>Generera ACA-rapporter i förmånshanteringen


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Förmånshanteringen spårar information som rapporteras i formulär 1095-B och formulär 1095-C för arbetsgivarmandatet för sjukförsäkring (ACA). Precis som ACA-rapporteringsfunktionerna i den gamla arbetsytan **Förmåner** gäller denna funktion endast juridiska personer i USA.

Om du vill använda den här funktionen måste du först aktivera **Avancerad förmånshantering**. Mer information, inklusive viktiga förbehåll angående förmånshantering, finns i [Aktivera eller inaktivera förmånshantering](hr-admin-manage-features.md#enable-or-disable-benefits-management).

> [!IMPORTANT]
> Du kan bara använda ACA-rapportering från antingen arbetsytan **Förmånshantering** eller den gamla arbetsytan **Förmåner**, men inte från båda. Om du till exempel har växlat till Förmånshantering blir ACA-rapporteringen bara tillgänglig från arbetsytan **Förmånshantering**, inte från den gamla arbetsytan **Förmåner**.
>
> Om du växlar till Förmånshantering mitt under ett registreringsår måste du konfigurera medarbetardata korrekt för hela året i Förmånshanteringen. På det här sättet ser du till att du får korrekt rapporteringsinformation för hela året.

## <a name="getting-started"></a>Komma igång

Om du vill spåra information för 1095-formulär måste du först skapa en eller flera disponeringsgrupper för sjukförsäkring. Grupperna visar följande information:

- Det disponeringserbjudande som medarbetaren har tillhandahållits
- Medarbetarens andel av den lägsta månadspremien, om kostnaden överstiger den federala fattigdomsgränsen
- De skyddsramar som används av arbetsgivaren, om tillämpligt

Med disponeringsgrupper för sjukförsäkring kan du hantera denna information för flera medarbetarposter med samma villkor. Du kan enkelt tilldela grupper till en eller flera medarbetare.

### <a name="create-or-edit-an-affordable-care-coverage-group"></a>Skapa eller redigera en disponeringsgrupp för sjukförsäkring

1. I arbetsytan **Förmånshantering** väljer du **Disponeringsgrupp för sjukförsäkring**.

    ![Välja disponeringsgrupp för sjukförsäkring.](./media/hr-benefits-management-aca-coverage-group.png)

2. Välj **Ny** om du vill skapa en ny disponeringsgrupp för sjukförsäkring, eller **Redigera** för att ändra en befintlig grupp.

    ![Välja Ny eller Redigera.](./media/hr-benefits-management-aca-new.png)

3. Ange följande fält.

    | Fält | beskrivning |
    |---|---|
    | Namn | Ange ett namn på gruppen. |
    | beskrivning | Ange en beskrivning för gruppen. |
    | Erbjudande om försäkringsskydd | Den omfattning som erbjuds medarbetare, dessas make/maka eller partner samt deras beroende. |
    | Medarbetarens del av kostnaden | Det belopp som medarbetaren är ansvarig för. |
    | Tillämplig safe harbor för avsnitt 4980H | 4980H-koden för skyddsramar eller kod för övergångslättnad. |
    | Planens startmånad | Välj den kalendermånaden när förmånsplanens år börjar. |
    | Grupp giltig från | Det första datum då posten är giltig. |
    | Grupp giltig till | Det sista datum då posten är giltig. Om det inte finns något utgångsdatum anger du **Aldrig**. |

    ![Skapa en disponeringsgrupp.](./media/hr-benefits-management-aca-new-group.png)

4. Välj **Spara**.

### <a name="assign-multiple-employees-to-an-affordable-care-coverage-group"></a>Tilldela flera medarbetare till en disponeringsgrupp för sjukförsäkring

1. I arbetsytan **Förmånshantering** väljer du **Disponeringsgrupp för sjukförsäkring**.
2. Välj den grupp som medarbetare ska tilldelas till.
3. Välj **Masstilldelning**.

    ![Välja Masstilldelning.](./media/hr-benefits-management-aca-mass-assignment.png)

4. Välj medarbetare i listan och välj sedan **Tilldela**.

    ![Tilldela valda medarbetare till en grupp.](./media/hr-benefits-management-aca-assign-coverage-group.png)

## <a name="maintain-multiple-versions-of-coverage-options"></a>Underhålla flera versioner av försäkringsskyddsalternativ

Du kan underhålla flera versioner av valfri försäkringsskyddsgrupp. När något ändras i organisationen eller bland de förmåner som erbjuds, kan du hålla gruppens information uppdaterad utan att behöva skapa en ny grupp och tilldela om medarbetare till den.

När du har skapat disponeringsgrupper för sjukförsäkring kan du masstilldela medarbetare till dem. Du kan också tilldela medarbetare till grupper individuellt och ange om ACA-information spåras och rapporteras.

Om du inte behöver spåra och rapportera ACA-information för en medarbetare, kan du ange alternativet **Rapportdisponering** som **Nej**. Du kanske till exempel har deltidsanställda som inte kräver ACA-rapportering.

### <a name="override-default-values-for-an-employee"></a>Åsidosätta standardvärden för en medarbetare

För medarbetare som tilldelats till en disponeringsgrupp för sjukförsäkring kan du ändra följande alternativ under samtliga månader som kräver olika värden:

- Erbjudande om försäkringsskydd
- Medarbetarens del av kostnaden
- Tillämplig safe harbor för avsnitt 4980H

> [!NOTE]
> För 2020 års ACA-rapporter måste du rapportera både arbets- och hempostnummer i formulär 1095-C. Värden fylls i automatiskt baserat på för tillfället aktiva platser. Om någon av dessa platser var annorlunda under någon del av året måste du åsidosätta värdet. Fältet **Postnummer** (rad 17) i rapport 1095-C fylls endast i om koden **Disponeringserbjudande** innehåller **1L** till **1Q** enligt följande:
>
> - **1L, 1M eller 1N:** Det primära postnumret för bostaden
> - **1O, 1P, 1Q:** Det primära postnumret för arbetsplatsen

Gör på följande sätt om du vill ange undantag för värden i en disponeringsgrupp för sjukförsäkring.

1. I arbetsytan **personalhantering** välj **länkar** och välj sedan **arbetare**.
2. Välj medarbetaren i listan.
3. På fliken **Anställning**, i avsnittet **Mer information**, väljer du **Disponering för sjukförsäkring**.

    ![Ändra alternativ för en enskild medarbetare.](./media/hr-benefits-management-aca-change-single-employee.png)

4. Välj **Redigera**.
5. Markera kryssrutan **Åsidosätt standard** och ändra sedan erforderliga värden efter behov för samtliga månader som måste ändras.

    ![Åsidosätta standardvärden.](./media/hr-benefits-management-aca-override-default.png)

6. Välj **Spara**.

## <a name="report-health-care-coverage"></a>Rapportera sjukvårdstäckning

Du måste spåra eventuell arbetsgivarsponsrad, självförförsäkrad sjukförsäkringstäckning för hel- och deltidsanställda. Inkludera varje medarbetare, tillsammans med sina beroende, i 1095-C-rapporten för de månader som de täcks.

Följ de här stegen när du vill ange om en förmånsplan måste rapporteras.

1. I arbetsytan **Förmånshantering** väljer du **Förmånsplaner**.
2. Välj den förmånsplan som ska rapporteras.
3. Välj **Redigera**.
4. Ställ in alternativet **Rapporteras under sjukförsäkringar** som **Ja**.

    ![Rapportera hälsovårdstäckning.](./media/hr-benefits-management-aca-report-coverage.png)

5. Välj **Spara**.

Om en medarbetare väljer sjukvårdstäckning för en beroende medarbetare, bestäms den beroende täckningsperiod av det datum då den beroende medarbetaren registrerades eller togs bort. Disponeringsdatum för beroende beräknas automatiskt baserat på perioden när den beroende var berättigad och aktiv i en plan under registreringsåret.

## <a name="generate-1095-b-and-1095-c-forms"></a>Generera 1095-B- och 1095-C-formulär

Du kan skapa ACA 1095-B- och 1095-C-formulär och sedan distribuera dessa till var och en av dina medarbetare. Du kan också generera formulär 1095-C och motsvarande 1094-C-överföringsfiler som skickas till Skatteverket.

1. I arbetsytan **Förmånshantering** väljer du **formuläret ACA 1095-B** eller **formuläret ACA 1095-C**.
2. Ändra parametrarna efter behov och välj sedan **OK**.

    > [!NOTE]
    > Om du skriver ut formulär 1095-C till mer än 500 anställda får du mer än en PDF-fil. Vi rekommenderar att du ökar värdet för fältet **Maximal filstorlek i megabyte** på sidan **Parametrar för dokumenthantering** till **150**. (Om du snabbt vill öppna den sidan använder du sökfältet i navigeringsfältet.)
    >
    > ![Ändra den maximala filstorleken.](./media/hr-benefits-management-aca-maximum-file-size.png)

3. Om du vill kontrollera rapporternas status och visa dem använder du sökfältet i navigeringsfältet för att öppna sidan **Jobb för elektronisk rapportering**.

    ![Söka efter sidan Elektroniska rapporteringsjobb.](./media/hr-benefits-management-aca-search-electronic-reporting-jobs.png)

4. Markera rapporten som du vill visa och välj sedan **Visa filer**.

    ![Visa filer.](./media/hr-benefits-management-aca-show-files.png)

5. Välj **Öppen**.

    ![Öppna en fil.](./media/hr-benefits-management-aca-open-file.png)

6. Öppna zip-filen i meddelandefältet som visas längst ned i webbläsaren och markera sedan rapporten. Du kan visa eller skriva ut PDF-filen.

    ![Exempelformulär 1095-C.](./media/hr-benefits-management-aca-1095-c-form.png)

## <a name="view-aca-coverage-information"></a>Visa information om ACA-disponering

Sidan **Sjukförsäkringstäckning** visar följande information:

- Medarbetare som är tilldelade till respektive disponeringsgrupp
- Medarbetare som inte behöver tas med i en rapport
- Ej tilldelade medarbetare

Följ stegen nedan om du vill visa denna information.

1. I arbetsytan **Förmånshantering** väljer du **Sjukförsäkringstäckning för medarbetare**.
2. I fältet **Gruppnamn** väljer du en grupp.

    ![Visa ACA-täckning.](./media/hr-benefits-management-aca-view-coverage.png)

Om något av standardvärdena från täckningsgruppen för sjukförsäkring har åsidosatts, visas en asterisk bredvid värdet som har ändrats. Om värdena för alla 12 månader är desamma och inte har åsidosatts, visas värdet i kolumnen **Samtliga 12 månader**.

Du kan visa medarbetare som är markerade som icke-rapporteringsbara för sjukförsäkring och som inte kommer att kräva ett 1095-C-formulär. I fältet **Filtrera efter** väljer du **Ej rapporteringsbar för sjukförsäkring**.

Du kan visa medarbetare som inte är tilldelade till någon grupp eller som är tilldelade till en utgången grupp. I fältet **Filtrera efter** väljer du **Ej tilldelad eller utgången grupp**.

### <a name="export-to-excel"></a>Exportera till Excel

Om du vill exportera någon av listorna till Microsoft Excel följer du dessa steg.

1. Välj knappen **Öppna i Microsoft Office**.
2. Välj **Tillfälligt register för HCM Personal för internt bruk**.
3. Välj **Hämta**.

### <a name="view-aca-reportable-dependents"></a>Visa ACA-pliktiga beroenden

Om du måste rapportera täckta personer eftersom du tillhandahåller självförsäkrad täckning, kan du visa beroende personer som omfattas av förmånsplaner och som har markerats som **pliktiga för sjukförsäkring**. I åtgärdsfönstret väljer du **Visa täckning för beroende person**.

![Visa beroendetäckning.](./media/hr-benefits-management-aca-view-dependent-coverage.png)

Taäckningsinformation för medarbetarens beroenden visas.

![Medförsäkringsskydd.](./media/hr-benefits-management-aca-dependents.png)

> [!NOTE]
> På sidan visas endast förmånsplaner som är markerade som **pliktiga för sjukförsäkring**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
