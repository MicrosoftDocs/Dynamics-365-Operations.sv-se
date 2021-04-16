---
title: Förbered programspecifika metadata för RCS och ER
description: I det här avsnittet beskrivs hur du förbereder programspecifika metadata för RCS (Regulatory Configuration Service) och elektronisk rapportering (ER).
author: NickSelin
ms.date: 04/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: f0501fd67da0cbc5c10171b55004cb7f4fd4fd16
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5743713"
---
# <a name="prepare-application-specific-metadata-for-rcs-and-er"></a>Förbered programspecifika metadata för RCS och ER

[!include[banner](../includes/banner.md)]

I det här avsnittet får du stegvisa exempel på följande uppgifter:

- [Förbered programdata att användas i RCS](#prepare-application-metadata-that-can-be-used-in-rcs)
- [Få åtkomst till programmets metadata med hjälp av ER-konfiguration](#access-application-metadata-by-using-an-er-configuration)
- [Få åtkomst till programmets metadata med hjälp av anslutna program](#access-application-metadata-by-using-connected-applications)

## <a name="prepare-application-metadata-that-can-be-used-in-rcs"></a>Förbered programdata att användas i RCS

Följande procedur visas hur användare som har rollen **Systemadministratör** eller **utvecklare av ekonomiska rapporter** kan skapa en konfiguration av elektronisk rapporterings (ER) konfiguration som innehåller metadata för program och som används för att utforma konfigurationer av ER-modellmappning i Regulatory Configuration Service (RCS). Exempel på konfigurationen för ER-modellmappning som skapats i det här exemplet kommer att användas till utländska handelstransaktioner.

För det här exemplet vill du använda RCS för att utforma en ER-lösning för programmet som genererar elektroniska dokument som innehåller information från affärsdomänen för utländsk handel. Om du vill ange mappningen mellan ER-datamodellen och källorna till de data som krävs måste du ha tillgång till programdata i RCS. Som en del av utformningen av processen att utforma ER-lösningen måste du konfigurera en ny konfiguration av ER-metadata som innehåller alla metadata som för närvarande krävs för att generera ER-rapporter för vald affärsdomän.

> [!NOTE]
> I det här exemplet ska du skapa en konfigurering för bildpunktföretaget, Litware, Inc. Dessa steg kan utföras i något företag.

1. Gå till **Organisationsadministration \> Arbetsytor \> Elektronisk rapportering**.
2. Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som **aktiv** och är tillgänglig. Om du inte ser den här konfigurationsleverantören ska du först slutföra proceduren [Skapa konfigurationsleverantörer och välj dem som aktiva](tasks/er-configuration-provider-mark-it-active-2016-11.md). 
3. Välj **Metadatakonfiguration**.
4. Välj **Skapa konfiguration**.
5. Ange ett namn i listrutan i fältet **namn**. I det här exemplet anger du **metadata för utländsk handel**.
6. Välj **Skapa konfiguration**.
7. Välj **Designer**.
8. Markera **Lägg till**.

    > [!NOTE]
    > Du kan välja alla metadata för antingen hela programmet eller valda modeller eller moduler. I ba fall ska du tänka på att följande metadata kommer att läggas till automatiskt i det här fallet: register över poster, uppräkningar och utökade datatypern (ETD:er). Om det behövs ytterligare typer av metadata måste de läggas till manuellt.

    Du måste lägga till vissa metadata relaterade till externa handelstransaktioner pch markera metadataelement manuellt.

9. Välj **Lägg till datakälla \> Tabellregister**.
10. Filtrera på ett värde för **Intrastat** i fältet **namn**.
11. Väljtabellregister **Intrastat**.
12. Välj **OK**.

    Du måste lägga till metadatainformation om Intrastat-tabellen med poster.

13. I trädet väljer du **Tabellregister Intrastat \> \>Relationer \> IntrastatCommodity (Tabellregister EcoResCategory)**.
14. Välj **Lägg till metadata**.

    > [!NOTE]
    > Du måste lägga till metadata för obligatoriska relationer för det valda register med poster manuellt.

15. Välj **Lägg till datakälla**.
16. Välj **uppräkning**.
17. Filtrera på ett värde för **IntrastatDirection** i fältet **namn**.
18. Välj posten **IntrastatDirection** enumeration.
19. Välj **OK**.
20. Välj **Spara**.
21. Stäng sidan.
22. Fyll i utkastet av konfigurationen av metadata;

    1. Välj **Ändra status \> Slutför**.
    2. Välj **OK**.
    3. Väljden slutförda versionen 1.

23. Exportera den slutförda versionen av metadata-konfigurationen från programmet som XML-fil:

    1. Välj **Kurs \> Exportera som XML-fil**.
    2. Välj **OK**.

Konfigurationen för ER-metadata sparas som filen **utländska handelsmetadata.xml**. Du kan nu importera den till RCS så att den kan användas som källa för metadata för den utländskahandels domänen. Utifrån den här informationen kan vi ange mappningen mellan programdata och ER-datamodell.

## <a name="access-application-metadata-by-using-an-er-configuration"></a>Få åtkomst till programmets metadata med hjälp av ER-konfiguration

Följande procedur visar hur en RCS.användare som har rollen **Systemadministratör** eller **Utvecklare av elektronisk rapportering** kan designa en ny ER-modellmappning genom att använda metadata från programmet. Programmetadata kommer att användas genom att använda en ER-metadatakonfiguration som innehåller en exempeluppsättning med metadata för att komma åt transaktioner i utländsk handel.

Innan du kan slutföra proceduren, måste du först slutföra följande procedurer:

- [Skapa konfigurationsleverantörer och markera dem som aktiva](tasks/er-configuration-provider-mark-it-active-2016-11.md)
- [Förbered programdata att användas i RCS](#prepare-application-metadata-that-can-be-used-in-rcs)

1. Gå till **Alla arbetsytor \> Elektronisk rapportering**.
2. Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som **aktiv** och är tillgänglig. Om du inte ser den här konfigurationsleverantören ska du först slutföra proceduren [Skapa konfigurationsleverantörer och välj dem som aktiva](tasks/er-configuration-provider-mark-it-active-2016-11.md). 
3. Importera ER-metadatakonfigurationen som innehåller metadata från programmet som är konfigurerat att generera elektroniska dokument för domäner för utländsk handel. Du har skapat den här ER-konfigurationen av metadata och exporterat den som en XML-fil i proceduren [Förbereda programmetadata som kan användas i RCS](#prepare-application-metadata-that-can-be-used-in-rcs) tidigare i det här avsnittet.

    1. Välj **Metadatakonfiguration**.
    2. Välj **kurs**
    3. Välj **Läs in från XML-fil**.
    4. Bläddra och välj filen **Utländsk handel metadata.xml**.
    5. Välj **OK**.
    6. Stäng sidan.

4. Skapa en datamodellskonfiguration

    1. Välj **rapporteringskonfigurationer**.
    2. Välj **Skapa konfiguration**.
    3. I listrutan i fältet **Namn** anger du **Utländsk handelsmodell**.
    4. Välj **Skapa konfiguration**.
    5. Välj **Designer**.
    6. Välj **Nytt** om du vill öppna dialogrutan.

        1. Ange **root** i fältet **Namn**.
        2. Markera **Lägg till**.
    
    7. Välj **Nytt** om du vill öppna dialogrutan.

        1. Ange **Transaktion** i fältet **Namn**.
        2. Välj **Postlista** i fältet **Artikeltyp**.
        3. Markera **Lägg till**.
 
    8. Välj **Nytt** om du vill öppna dialogrutan.

        1. Ange **Artikelkod** i fältet **Namn**.
        2. Välj **Sträng** i fältet **Artikeltyp**.
        3. Markera **Lägg till**.

    9. Välj **Nytt** om du vill öppna dialogrutan.

        1. Ange **Fakturerat belopp** i fältet Namn.
        2. Välj **Realtal** i fältet **Artikeltyp**.
        3. Markera **Lägg till**.

    10. Välj **Nytt** om du vill öppna dialogrutan.

        1. Ange **Datum** i fältet **Namn**.
        2. Välj **Datum** i fältet **Artikeltyp**.
        3. Markera **Lägg till**.
 
    11. Välj **Lägg till \> Rotreferens**.
    12. Välj **OK**.
    13. Välj **Spara**.
    14. Stäng sidan.
    15. Välj **Ändra status \> Slutför**.
    16. Välj **OK**.

5. Skapa konfiguration av modellmappning:

    1. Välj **Skapa konfiguration**.
    2. I listrutan i fältet **Ny** anger du **Modellmappning baserat på datamodellens utländsk handelsmodell**.
    3. Ange **Utländsk handelsmappning** i fältet **Namn**.
    4. Välj **Skapa konfiguration**.
    5. På snabbfliken **förutsättningar** väljer du **redigera**.
    6. Välj **Ny**.
    7. Välj **konfiguration** i fältet **förutsättningskomponenttyp**.
    8. Välj konfiguration av **metadata för utländsk handel**.
    9. Välj **Spara**. Observera att referensen läggs till version 1 av konfigurationen **metadata för utländsk handel**. Programdata från denna konfiguration kommer att erbjudas när modellmappningen kommer att vara konstruerad.
    10. Stäng sidan.
    11. Välj **Designer**.
    12. Välj **Designer**.
    13. I trädet väljer du **Dynamics 365 for Operations \> Tabellregister**.
    14. Välj **Lägg till rot**.
    15. Skriv **Dokument** i fältet **Intrastat**.
    16. Välj tabellregister **Intrastat**.
    17. Välj **OK**.

        > [!NOTE]
        > Endast två tabeller erbjöds eftersom de enda två tabellerna lades till i uppsättningen metadata som används.

    18. Välj **bind**.
    19. I trädet väljer du **Intrastat \> AmountMST**.
    20. I trädet väljer du **Transaktion = Intrastat \> Fakturerat belopp**.
    21. Välj **bind**.
    22. I trädet väljer du **Intrastat \> TransDate**.
    23. I trädet väljer du **Transaktion = Intrastat \> Datum**.
    24. Välj **bind**.
    25. I trädet väljerdu **Intrastat \> \>Relationer \> IntrastatCommodity \> Kod**.
    26. I trädet väljer du **Transaktion = Intrastat \> Artikelkod**.
    27. Välj **bind**.
    28. Välj **validera**.

        > [!NOTE]
        > När valideringen är slutförd har du bundit element i datamodellen med objekt av datakällor som beskrivs genom att använda information om programdata från den ER-metadatakonfiguration som refereras till.

    29. Välj **Spara**.

När du behöver utöka den befintliga uppsättningen metadata kan du göra det i programmet. Sedan kan du exportera den nya slutförda versionen av konfigurationen för ER-metadata från, importera den till RCS och uppdatera förutsättningarna för den konfigurerade modellmappningskonfigurationen som hänvisar till en ny version av importerad metadatakonfiguration.

> [!NOTE]
> Det här sättet att hämta information om programdata det enda som är tillgängligt för lokalt distribuerade program (när lokala affärsdata \[LBD\] eller lokalt, distributionsmodell används för programmet).

## <a name="access-application-metadata-by-using-connected-applications"></a>Få åtkomst till programmets metadata med hjälp av anslutna program

Följande procedur visar hur en RCS.användare som har rollen **Systemadministratör** eller **Utvecklare av elektronisk rapportering** kan designa en ny ER-modellmappning genom att använda metadata från programmet. Programdata kan nås online genom att använda det RCS-anslutna programmet. Exempel på ER-modellmappning kommer att konfigureras för åtkomst till utländska handelstransaktioner.

För att slutföra den här proceduren måste du först slutföra stegen i proceduren [Skapa konfigurationsleverantörer och markera dem som aktiva](tasks/er-configuration-provider-mark-it-active-2016-11.md) i RCS. Om du inte har slutfört proceduren [Få åtkomst till programdata genom att använda ER-konfiguration](#access-application-metadata-by-using-an-er-configuration), gå till sidan [Elektroniska rapporteringsguider för Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) för att hämta och spara följande ER-konfigurationsfiler i förväg och spara dem lokalt; **Utländsk handel metadata.xml**, **Utländsk handel model.xml**; **Utländsk handel mapping.xml** och slutför sedan stegen i proceduren.


### <a name="get-required-er-configurations"></a>Skapa nödvändiga ER-konfigurationer

Om du redan har slutfört proceduren [Få åtkomst till programdata genom att använda ER-konfiguration](#access-application-metadata-by-using-an-er-configuration) tidigare i det här ämnet har du redan alla ER-konfigurationer som krävs (metadata för utländsk handel, modell- och mappningskonfiguration) i den aktuella RCS-instansresursen. I så fall kan du hoppa över den här proceduren.

1. Gå till **Alla arbetsytor \> Elektronisk rapportering**.
2. Välj **rapporteringskonfigurationer**.
3. Läs in konfigurationsfilerna **metadata för utländsk handel.xml**, **utländsk handelsmodell.xml** och **mappning till utländsk handel.xml** som upprepar följande steg för var och en av dem:

    1. Välj **kurs**
    2. Välj **Läs in från XML-fil**.
    3. välj **Bläddra** och välj en fil.
    4. Välj **OK**.

### <a name="register-the-connection-with-the-application"></a>Registrera anslutningen till programmet

1. Gå till **Alla arbetsytor \> Elektronisk rapportering**.
2. Välj **anslutna program**.
3. Kontrollera att det konfigurerade programmet är baserat på Microsoft Azure och att det är tillgängligt i allmänhet för att RCS-användare. Den aktuella RCS-användaren måste ha åtkomst till det konfigurerade programmet och registrerats som en användare av det här programmet som ger behörighet att komma åt programmets metadata.
4. Välj **Ny**.
5. Ange **MyConnectedApp** som namnet på det kopplade programmet i fältet **Namn**.
6. Ange URL för programmet i fältet **Program**.
7. Ange leverantör för programmet i fältet **Klientorganisation**.
8. Välj **Spara**. 
9. När du kontrollerar anslutningen till ett konfigurerat program klickar du på sidan **Anslut till fjärrprogram**, välj länken **Välj här för att ansluta till valt fjärrprogram**. 
10. Välj **kontrollera anslutningen** för att verifiera åtkomst till det konfigurerade programmet.
11. Välj **Nära**.

När du har avslutat proceduren och anslutningsvalideringen är klar uppdateras informationen om version och klientorganisation för det konfigurerade programmet i det aktuella rutnätet.

### <a name="review-the-existing-model-mapping-configuration"></a>Granska befintlig konfiguration för mappning

1. Gå till **Alla arbetsytor \> Elektronisk rapportering**.
2. Välj **rapporteringskonfigurationer**.
3. I trädet väljer du **Utländsk handelsmodell \> Utländsk handelsmappning**.
4. Välj snabbfliken **förutsättningar**.

    > [!NOTE]
    > Denna mappning refererar till konfigurationen för metadata. Programdata från denna konfiguration kommer att erbjudas när modellmappningen kommer att vara konstruerad.

4. Välj **Designer**.
5. Välj **Designer**.
6. I trädet väljer du **Dynamics 365 for Operations \> Tabellregister**.
7. Välj **Lägg till rot**.
8. Ange eller välj ett värde i fältet **Register**.

    > [!NOTE]
    > Denna mappning refererar till konfigurationen för metadata. Programdata från denna konfiguration kommer att erbjudas när modellmappningen kommer att vara konstruerad.

9. Välj **Avbryt**.

### <a name="assign-the-connected-application-to-a-model-mapping"></a>Tilldela kopplat program till modellmappning

1. Välj **Redigera**.
2. I **fältet kopplat program** väljer du programmet **MyConnectedApp**.

    > [!NOTE]
    > Denna mappning refererar till metadata för det markerade anslutna programmet. Om en mappning refererar till metadatakonfigurationen och det anslutna programmet samtidigt, används metadata för det anslutna programmet.

3. Välj **Designer**.
4. Välj **Designer**.
5. I trädet väljer du **Dynamics 365 for Operations \> Tabellregister**.
6. Välj **Lägg till rot**.
7. Ange eller välj ett värde i fältet **Register**.

    > [!NOTE]
    > Nu erbjuds mer än två programtabeller eftersom mappningen använder alla metadata för det anslutna program som har tilldelats för det.

8. Välj **Avbryt**.
9. Välj **validera**.

Du har bundit element i datamodellen med objekt av datakällor som beskrivs genom att använda information om metadata för det anslutna program som har tilldelats den här mappningen.

När du behöver utvärdera den här modellmappningen med hjälp av metadata i ett annat versionsprogram, registrerar du ett annat anslutet program, tilldelar det till den här modellmappningen och validerar det mot nya metadata.

## <a name="additional-resources"></a>Ytterligare resurser

Du kan också spela upp uppgiftsguiden **förbereda programmetadata som kan användas i RCS** i programmet och uppgiftsguiderna **Få åtkomst till programmets metadata med hjälp av en ER-konfiguration** och **Få åtkomst till programmetadata med hjälp av kopplade program** i RCS. De här uppgiftsguiderna kan hämtas på sidan [uppgiftsguiden elektronisk rapportering för Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]