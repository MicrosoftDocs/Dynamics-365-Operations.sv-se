---
title: Få åtkomst till programmets metadata med hjälp av ER-konfiguration
description: Stegen i det här avsnittet beskriver hur en RCS-användare (Regulatory Configuration Service) kan utforma en ny ER-modellmappning genom att använda metadata i Finance and Operations.
author: NickSelin
manager: AnnBe
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fa8e9ac4940bbc1252819ebcc3de2e21c9e0933f
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682175"
---
# <a name="access-application-metadata-by-using-er-configuration"></a>Få åtkomst till programmets metadata med hjälp av ER-konfiguration

[!include [banner](../../includes/banner.md)]

I följande steg förklaras hur en användare av Regulatory configuration service (RCS) i rollen Systemadministratör eller Utvecklare av elektronisk rapportering kan utforma en ny modellmappning för elektronisk rapportering (ER) genom att använda metadata i programmet. Programmetadata kommer att användas genom att använda en ER-metadatakonfiguration som innehåller en exempeluppsättning med metadata för att komma åt transaktioner i utländsk handel. För att slutföra dessa steg, i RCS måste du först slutföra stegen i ämnet [Skapa en konfigurationsleverantörer och välj de som aktiva](er-configuration-provider-mark-it-active-2016-11.md) Slutför sedan stegen i ämnet [Förbered programmetadata att användas i RCS](prepare-application-metadata-rcs.md).

## <a name="prerequisites"></a>Förutsättningar
1. Gå till **Alla arbetsytor** > **Elektronisk rapportering**. 
2. Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som **aktiv** och är tillgänglig. Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren [Skapa konfigurationsleverantörer och välj dem som aktiva](er-configuration-provider-mark-it-active-2016-11.md). 

## <a name="import-metadata-configuration"></a>Importera metadatakonfiguration 
1. Klicka på **Metadatakonfiguration**. 
2. Importera ER-metadatakonfigurationen som innehåller metadata har konfigurerats för att generera elektroniska dokument för utländsk handel. Denna ER-metadatakonfiguration har exporterats som XML-fil medan stegen i [Förbered programmetadata för användning i RCS](prepare-application-metadata-rcs.md)-proceduren har slutförts. 
3. Klicka på **Byt**. 
4. Klicka på **Läs in från XML-fil**. 
5. Klicka på **Bläddra** och välj filen Utländsk handel metadata.xml. 
6. Klicka på **OK**. 
7. Stäng sidan. 

## <a name="create-data-model-configuration"></a>Skapa en datamodellskonfiguration
1. Klicka på **Rapporteringskonfiguration**. 
2. Klicka på **Skapa konfiguration** om du vill öppna dialogrutan. 
3. Ange "Foreign trade model" i fältet **Namn**. 
4. Klicka på **Skapa konfiguration**. 
5. Klicka på **Designer**. 
6. Klicka på **Nytt** om du vill öppna dialogrutan. 
7. Ange "Root" i fältet **Namn**. 
8. Klicka på **Lägg till**. 
9. Klicka på **Nytt** om du vill öppna dialogrutan. 
10.    Ange "Transaction" i fältet **Namn**. 
11.    Välj **Postlista** i fältet **Artikeltyp**. 
12.    Klicka på **Lägg till**. 
13.    Klicka på **Nytt** om du vill öppna dialogrutan. 
14.    Ange "Commodity code" i fältet **Namn**. 
15.    Välj **Sträng** i fältet **Artikeltyp**. 
16.    Klicka på **Lägg till**. 
17.    Klicka på **Nytt** om du vill öppna dialogrutan. 
18.    Ange "Invoiced amount" i fältet **Namn**. 
19.    Välj **Realtal** i fältet **Artikeltyp**. 
20.    Klicka på **Lägg till**. 
21.    Klicka på **Nytt** om du vill öppna dialogrutan. 
22.    Ange "Date" i fältet **Namn**. 
23.    Välj **Datum** i fältet **Artikeltyp**. 
24.    Klicka på **Lägg till**. 
25.    Klicka på **Rotreferens**. 
26.    Klicka på **OK**. 
27.    Klicka på **Spara**. 
28.    Stäng sidan. 
29.    Klicka på **Ändra status**. 
30.    Klicka på **Slutför**. 
31.    Klicka på **OK**. 

## <a name="create-model-mapping-configuration"></a>Skapa konfiguration av modellmappning 
1. Klicka på **Skapa konfiguration** om du vill öppna dialogrutan. 
2. Ange "Model Mapping based on Foreign trade model" i fältet **Ny**. 
3. Ange "Foreign trade mapping" i fältet **Namn**. 
4. Klicka på **Skapa konfiguration**. 
5. Expandera avsnittet **Förutsättningar**. 
6. Klicka på **Redigera**. 
7. Klicka på **Ny**. 
8. Markera vald rad i listan. 
9. Välj **konfiguration** i fältet **förutsättningskomponenttyp**. 
10.    Välj konfiguration av **metadata för utländsk handel**. 
11.    Klicka på **Spara**. 
12.    Referensen till version 1 av konfigurationen av metadata för utländsk handel lades till i version 1. Programdata från denna konfiguration kommer att erbjudas när modellmappningen kommer att vara konstruerad. 
13.    Stäng sidan. 
14.    Klicka på **Designer**. 
15.    Klicka på **Designer**. 
16.    Välj **Dynamics 365 for Operations\Tabellregister** i trädet. 
17.    Klicka på **Lägg till rot**. 
18.    Ange "Intrastat" i fältet **Namn**. 
19.    Välj tabellregister **Intrastat**. 
20.    Klicka på **OK**. 

> [!NOTE]
> De enda 2 tabellerna erbjöds eftersom de enda två tabellerna lades till i uppsättningen metadata som används för tillfället. 

21.    Klicka på **Bind**. 
22.    Expandera **Intrastat** i trädet. 
23.    I trädet väljer du **Intrastat\AmountMST**. 
24.    Expandera **Transaktion = Intrastat** i trädet. 
25.    Välj **Transaktion = Intrastat\Fakturerat belopp** i trädet. 
26.    Klicka på **Bind**. 
27.    I trädet väljer du **Intrastat\TransDate**. 
28.    I trädet väljer du **Transaktion = Intrastat\Datum**. 
29.    Klicka på **Bind**. 
30.    I trädet expanderar du **Intrastat\>Relationer**. 
31.    I trädet expanderar du **Intrastat\>Relations\IntrastatCommodity**. 
32.    I trädet expanderar du **Intrastat\>Relations\IntrastatCommodity\Code**. 
33.    Välj **Transaction = Intrastat\Commodity code** i trädet. 
34.    Klicka på **Bind**. 
35.    Klicka på **Validera.** 

> [!NOTE]
> Vi har bundit element i datamodellen med objekt av datakällor som beskrivs genom att använda information om programdata från den ER-metadatakonfiguration som refereras till. 
36.    Klicka på **Spara**. 
37.    Stäng sidan. 
38.    Stäng sidan. 
39.    Om det behövs kan du utöka den befintliga uppsättningen metadata och sedan exportera den nya slutförda versionen av konfigurationen för ER-metadata. Du kan sedan importera den till RCS och uppdatera förutsättningarna för den konfigurerade modellmappningskonfigurationen som hänvisar till en ny version av importerad metadatakonfiguration. 

> [!NOTE]
> Det här sättet att hämta information om programdata det enda som är tillgängligt för lokalt distribuerade program (när lokala affärsdata (LBD) eller lokalt, distributionsmodell används).
        
