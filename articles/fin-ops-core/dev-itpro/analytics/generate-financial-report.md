---
title: Skapa ekonomiska rapporter
description: Det här avsnittet innehåller allmän information om att skapa en ekonomisk rapport.
author: jinniew
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 68843
ms.assetid: 271df6f4-12b7-4b3e-b2d7-36ea98ef1871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: c6cde37124d4a3337bca2a9b445af5fdfd87f453
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750020"
---
# <a name="generate-financial-reports"></a>Skapa ekonomiska rapporter

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller allmän information om att skapa en ekonomisk rapport.

Öppna rapportdefinitionen och klicka sedan på knappen **Generera** i verktygsfältet om du vill skapa en rapport. Sidan **Rapportköstatus** öppnas och visar platsen för rapporten i kön. Som standard öppnas rapporten i Web Viewer.

Följande alternativ är tillgängliga för rapportgenerering:

- Ställa in ett schema för att skapa en rapport eller en grupp av rapporter automatiskt
- Kontrollera om det saknas konton eller data i en rapport och validera riktigheten i en rapport

När du skapar en rapport används de alternativ du har angett på fliken Rapportdefinition.

## <a name="generate-a-financial-report"></a>Generera ekonomisk rapport

För att skapa en ekonomirapport, gå till **redovisning** \> **förfrågningar och rapporter** \> **ekonomirapporter**.

- Välj en rapport att skapa och klicka på **Skapa**.
- Fyll i fältet **Rapportdatum** och klicka på **OK**.

När rapporten har skapats blir den tillgänglig i avsnittet **Rapporter**.

Du kan välja att **Visa** eller **Ta bort** rapporten.

Att skapa en rapport med **Rapportdesigner**, öppna rapportdefinition och välj knappen **Generera** på verktygsfältet. Sidan **Rapportköstatus** öppnas och visar platsen för rapporten i kön. Som standard öppnas rapporten i Web Viewer.

## <a name="report-groups"></a>Rapportgrupper

Rapportgrupper är ett effektivt sätt att generera flera rapporter samtidigt. Anta att dina användare genererar åtta rapporter varje månad vid månadsslut. Skapa en rapportgrupp och du kan välja **Generera** för var och en av de åtta rapporterna i gruppen kan du välja **Generera** för rapportgruppen och de åtta rapporterna genereras i ett steg. När rapporterna i den valda rapportgruppen har genererats kan du gå till **Ekonomiska rapporter** (**Redovisning > Förfrågningar och rapporter > Ekonomiska rapporter**) för att visa de enskilda rapporterna. Slutför följande steg för att skapa en rapportgrupp.

1. Välj i Rapportdesigner **Rapportgrupper**. 
2. Välj de befintliga rapportdefinitioner som ska inkluderas i rapportgruppen. 
3. Välj inställningar för åsidosättningsföretag, detaljer och datum för var och en av rapporterna som ska ingå i gruppen.
   Vi rekommenderar att du **Företag**, **Period**, **År** och **Detaljnivå** för varje rapport. 
4. Spara rapportgruppen.

## <a name="schedule-report-generation"></a>Schemalägga rapporter
Många företag har en serie grundläggande rapporter som körs regelbundet vid schemalagda tidpunkter som en del av affärsprocesserna. Du kan schemalägga en rapport som ska skapas en gång om dagen, en gång i veckan eller månaden eller årligen. Det kan vara en enstaka rapport eller en grupp rapporter som inbegriper flera företag. Du måste ange dina autentiseringsuppgifter för vart och ett av företagen du anger, t.ex. sådana i en rapportträdsdefinition. Om autentiseringsuppgifterna är ogiltiga visas endast den information du har behörighet att komma åt i rapporterna, t.ex. det aktuella företag du är inloggad i för tillfället. Utdatainformationen läses först från rapportgruppen och sedan från de enskilda rapporterna.

De rapportscheman som skapas och sparas visas under Rapportscheman i navigationsfönstret. Du kan ordna rapporterna i mappar som du skapar. Om en enstaka rapport i ett schema inte skulle köras, körs ändå de övriga av schemats rapporter.

> [!IMPORTANT]
> Du måste ha designer- eller administratörsrollen för att kunna skapa, ändra och ta bort rapportscheman. När en rapport körs skapas den med hjälp av autentiseringsuppgifterna för den användare som skapade schemat.

### <a name="create-a-report-schedule"></a>Skapa ett rapportschema

1. Klicka på **Nytt** på **Arkiv**-menyn i Report Designer och välj sedan **Rapportschema**. Dialogrutan **Nytt rapportschema** öppnas.
2. Markera en enskild rapport eller en rapportgrupp som du vill schemalägga under **Inställningar**. De rapporter och rapportgrupper som visas gäller endast för det valda företaget eller byggblocket som du för närvarande är inloggad i.
3. Aktivera rapportschemat genom att markera kryssrutan **Aktivt**. Det är endast den som har skapat rapporten eller en administratör som kan aktivera eller inaktivera ett rapportschema.
4. Ange företagets autentiseringsuppgifter genom att klicka på knappen **Behörigheter**. Som standard används din inloggningsinformation för företaget som du är inloggad i. Om även andra företag är inbegripna, t.ex. som i rapportträdsdefinitioner, markerar du **Använd andra autentiseringsuppgifter** och anger sedan autentiseringsuppgifterna för andra företag som ingår i rapportschemat. Du kan markera **Windows-autentisering** eller skriva ett användarnamn och lösenord för varje företag. Markera kryssrutan **Spara autentiseringsuppgifter** om du vill spara företagens uppgifter och stäng sedan dialogrutan genom att klicka på **OK**.
5. Välj det datum när schemat ska börja i fältet **Början av återkommande** under **Frekvens**. Klientdatorns aktuella systemdatum är förvalt som standard.
6. Välj den tidpunkt när rapporten ska köras i fältet **Kör rapport**. Om du anger en tidpunkt som ligger tidigare än aktuell systemtid körs rapporten på följande schemalagda datum.
7. Ange hur ofta rapporten ska köras i området **Upprepningsmönster**. **Daglig** väljs som standard, med ett intervallvärde (dagar) på 1. Andra alternativ inkluderar Veckovis, Månadsvis och Årligen.
8. Välj när rapporten ska upphöra att genereras i området Intervall för återkommande.

    - **Slutdatum saknas** – Rapportschemat körs tills vidare.
    - **Ange antal förekomster** – Rapportsschemat körs angivet antal gånger och sedan inaktiveras det.
    - **Sluta den** – Rapportschemat slutar på angivet datum.

9. Välj **Spara**. Skriv ett unikt namn och en beskrivning för rapportschemat i dialogrutan **Spara som**.

Du måste ha designer- eller administratörsrollen för att kunna kopiera ett rapportschema. Även om en administratör skulle ändra rapportschemat behåller rapporten autentiseringsuppgifterna för den användare som skapade rapporten.

### <a name="copy-a-report-schedule"></a>Kopiera ett rapportschema

1. Klicka på **Rapportscheman** i navigeringsfönstret i Report Designer och öppna en rapport som du vill kopiera.
2. Klicka på **Spara som** på **Arkiv**-menyn och ange sedan ett nytt namn och beskrivning för schemat i dialogrutan **Spara som**. Det nya schemat visas i navigeringsfönstret när du klickar på **OK**.
3. Ändra fälten och informationen i det nya schemat efter behov och klicka sedan på **Spara** i verktygsfältet eller klicka på **Spara** på **Arkiv**-menyn.

Du måste vara ägare till rapportschemat eller ha administratörsrollen för att kunna ta bort ett rapportschema.

### <a name="delete-a-report-schedule"></a>Ta bort ett rapportschema

1. Klicka på **Rapportscheman** i navigeringsfönstret i rapportdesigner.
2. Markera det rapportschema som du vill ta bort och klicka sedan på **Ta bort** eller tryck på **Delete**-tangenten.
3. Om du vill ta bort rapportschemat permanent klickar du på **Ja** i dialogrutan där du bekräftar borttagningen. Skulle du sakna behörighet att ta bort schemat visas ett meddelande och rapporten behålls.

### <a name="credentials-and-report-schedules"></a>Användarinformation och rapporttidsplaner

Om du inte anger de autentiseringsuppgifter som krävs för alla företag som omfattas av rapporterna visas följande felmeddelande när du sparar rapportschemat: ”Du måste ange autentiseringsuppgifter för företagen som ingår i det här rapportschemat. Ange autentiseringsuppgifterna genom att klicka på knappen Behörigheter.”

Exempel: Användaren loggar in i företag A med sitt användarnamn och lösenord. Användaren skapar ett schema för en rapport där en rapportträdsdefinition används för att samla in data från flera företag. När rapporten sparas uppmanas användaren ange autentiseringsuppgifterna för de andra angivna företagen i rapportträdsdefinitionen. Om dina autentiseringsuppgifter upphör att gälla skapas inte de rapporter i rapportschemat som påverkas förrän autentiseringsuppgifterna har uppdaterats. Det visas ett meddelande i rapportkön om att behörigheterna måste uppdateras. Körningen av rapportschemat misslyckas om något av följande inträffar (på grund av krav på autentiseringsuppgifter):

- Ett nytt företag har lagts till i ett rapportträd för en enskild rapport.
- En rapport i en rapportgrupp har ändrats.
- En ny rapport för ytterligare ett företag har lagts till i en rapportgrupp.

Du fortsätter genom att klicka på knappen **Behörigheter** i dialogrutan **Schemalägg rapport**, och sedan skriver du lämpliga autentiseringsuppgifter.

## <a name="missing-account-analysis-feature"></a>Funktionen analys av saknade konton
Om det eventuellt saknas ekonomiska konton och dimensioner kan du söka efter dem i alla raddefinitioner, rapportträdsdefinitioner en byggblocksgrupp. Den här funktionen är praktisk om du skapar eller uppdaterar flera konton eller byggblock under kort tid och behöver kunna kontrollera att all ny information finns i rapporterna.

Saknade konton fastställs med hjälp av raddefinitionens eller rapportträdsdefinitionens lägsta och högsta värden. Därefter visas en lista över konton som finns i ekonomidata, men saknas i raddefinitionen eller rapportträdsdefinitionen. Saknade konton med värden som överstiger eller understiger raddefinitionens värden inkluderas inte i listan med saknade konton.

> [!TIP]
> Av verifieringsskäl bör den här processen köras innan du skapar månadsrapporter och när du skapar nya byggblock.

Risken för saknade konton är lägre om du använder rapporter som innehåller värdeintervall. Använd om möjligt intervall i byggblocket så att nya konton som skapas kan inkluderas. Om någon rapportdefinition har inställningen @ANY företag kan du logga in i ett visst företag och köra en analys av saknade konton för företaget.

> [!NOTE]
> Om ett nytt företag har lagts till i måste du lägga till det i alla befintliga rapporters rapportträd för att det ska inkluderas i analysen av saknade konton.

### <a name="run-missing-account-analysis"></a>Kör analys av saknade konton

1. Klicka på **Verktyg** i Report Designer och klicka sedan på **Analys av saknade konton**.
2. Välj ett företag som du vill filtrera resultatet efter i fältet **Företagsfilter** eller välj **Alla (inget filter)** om du vill visa resultat från alla tillgängliga företag.
3. Välj den dimension som du vill filtrera resultatet efter i fältet **Dimensionsfilter** eller välj **Alla (inget filter)** om du vill visa samtlig dimensionsinformation för alla tillgängliga dimensioner.
4. Välj ett alternativ för sortering av resultatet i fältet **Gruppera efter**. Du kan sortera resultatet efter det byggblock som påverkas eller efter dimension och värdemängder.
5. Granska det resultat som visas. Om du markerar ett objekt i det övre fönstret visas ytterligare information om undantaget i det nedre fönstret. Den omfattar relaterade dimensioner, värden och rapporter.
6. Du öppnar det objekt som påverkas genom att klicka på dess ikon i listfönstret eller genom att högerklicka på objektet och sedan välja **Öppna**. Om du vill markera flera objekt håller du ned **Ctrl**-tangenten samtidigt markerar objekten i det nedre fönstret.
7. Om resultatet innehåller värden, byggblock eller rapporter som inte ska ingå i analysen högerklickar du på dessa och väljer **Ta inte med**. Du kan även markera kryssrutan **Ta inte med** intill objektet så att det tas bort ur listan. Undantagna objekt tas bort när listan uppdateras. Om du vill markera flera objekt håller du ned **Ctrl**-tangenten samtidigt markerar objekten i det nedre fönstret. Om du vill visa alla objekt, inklusive resultat som du tidigare har valt att inte ta med i analysen markerar du kryssrutan **Visa byggblock och värden som har exkluderats** och klickar sedan på **Uppdatera**.
8. Klicka på **Uppdatera** för att uppdatera undantag som du har markerat. Klicka på **Ja** om du vill uppdatera hela resultatet eller klicka på **Nej** om du bara vill uppdatera markerade objekt.

    > [!NOTE]
    > Om formuläret inte har öppnats de senaste 15 minuterna uppdateras det automatiskt när det öppnas.

9. När du har åtgärdat problemen stänger du dialogrutan genom att klicka på **OK**.

## <a name="keyboard-shortcuts-for-missing-account-analysis"></a>Tangentbordsgenvägar för analys av saknade konton
Du kan använda följande tangentbordsgenvägar när du kör en analys av saknade konton.

| Om du vill göra detta                           | Tryck på  |
|--------------------------------------|----------------------------|
| Filtrera efter företag                    | Alt+C                      |
| Filtrera efter dimension                  | Alt+D                      |
| Gå till fältet Gruppera efter            | Alt+G                      |
| Visa undantagna block och värden      | Alt+S                      |
| Uppdatera resultatet                      | Alt+R                      |
| Undanta det markerade byggblocket  | Alt+X                      |
| Undanta den markerade raddefinitionen  | Ctrl+B                     |
| Undanta det markerade dimensionsvärdet | Ctrl+D                     |
| Öppna den markerade rapportdefinitionen  | Ctrl+R                     |
| Öppna den markerade raddefinitionen     | Ctrl+O                     |


## <a name="additional-resources"></a>Ytterligare resurser

[Ekonomisk rapportering](financial-reporting-intro.md)

[Användargränssnitt i Report Designer](report-designer-interface.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
