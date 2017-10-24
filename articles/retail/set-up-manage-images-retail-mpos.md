---
title: "Ställa in och hantera bilder för Retail Modern POS"
description: "Den här artikeln beskriver stegen som ingår i hur du ställer in och hanterar avbildningar för de olika entiteterna som visas i Retail Modern POS (MPOS)."
author: athinesh99
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 52851
ms.assetid: 5c21385e-64e0-4091-98fa-6a662eb33010
ms.search.region: global
ms.search.industry: Retail
ms.author: athinesh
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2ec39137bcc68bd7d9b71f6798474e88fb89fd1e
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-and-manage-images-for-retail-modern-pos"></a>Ställa in och hantera bilder för Retail Modern POS

[!include[banner](includes/banner.md)]


Den här artikeln beskriver stegen som ingår i hur du ställer in och hanterar avbildningar för de olika entiteterna som visas i Retail Modern POS (MPOS).

<a name="setting-up-the-media-base-url-and-defining-media-templates-to-configure-the-format-for-image-urls"></a>Ställa in mediebaserad URL och definiera mediamallar för att ställa in format för bild-URL
-------------------------------------------------------------------------------------------------

Bilderna som anges i Retail Modern POS (MPOS) måste vara värdlagrade externt, utanför Microsoft Dynamics 365 for Retail. Normalt lagras de i ett innehållshanteringssystem, innehållsleveransnätverk (CDN) eller en mediaserver. MPOS hämtar och visar då bilderna för lämpliga enheter, till exempel produkter och kataloger, genom att få åtkomst till mål-URL. Om du vill hämta dessa externt värdbaserade bilder kräver MPOS korrekt URL-format för bilderna. Du kan konfigurera obligatoriskt URL-format för bilderna genom att ställa in värdet **Mediabas-URL** i kanalprofilen och använda funktionen **Definiera mediamall** för varje enhet. Du kan även skriva över det vanliga URL-formatet för en undergrupp av enheter, genom att använda funktionen **Redigera i Excel**. **Obs!** I den aktuella versionen av Dynamics 365 for Retail kan du inte längre ställa in URL-formatet genom att använda **Bild**-attribut-XML för MPOS i attributgruppen **Standard** för enheter. Om du har kunskaper om Microsoft Dynamics AX 2012 R3 och använder den aktuella versionen av Dynamics 365 for Retail, se till att du använder alltid den nya **Definiera mediamallen**-funktionen för att ställa in bilder. Använd inte eller ändra **Bild**-attributet i **Standard**-attributgruppen för enheter, inklusive produkter. De ändringar du gör direkt i **Standard**-attributgruppen för bilder kommer inte reflekteras. Detta alternativ kommer avaktiveras i en kommande version. I följande procedurer ställs in bilder för katalogenheten till exempel. Dessa procedurer hjälper dig att garantera att rätt bildmålsökväg anges obetingat för alla katalogbilder som använder en gemensam sökväg. Till exempel, om du har ställt in en mediaserver eller en CDN externt, och vill att bilderna att visas i MPOS för en viss butik, **Definiera mediamallen**-funktionen hjälper dig ställa in sökvägen, där MPOS kan slås upp, och att hämta bilderna. **Notering:** I detta demonstrationsdataexempel distribueras mediaservern på Retail Server. Du kan dock ha den någonstans utanför Dynamics 365 for Retail.

### <a name="set-up-the-media-base-url-for-a-channel"></a>Ställ in mediebas-URL för en kanal

1.  Öppna Dynamics 365 for Retail HQ portal.
2.  Klicka på **Butik** &gt; **Kanalinställningar** &gt; **Kanalprofiler**. [![kanalprofil1](./media/channel-profile1.png)](./media/channel-profile1.png)
3.  I kanalprofilen, som din butik använder för MPOS, uppdatera **Mediabas-URL**-fältet med bas-URL för din mediaserver eller CDN. Bas-URL är den första delen av URL som delas av alla bildmappar för olika enheter.[![kanalprofil2](./media/channel-profile2.png)](./media/channel-profile2.png)

### <a name="define-the-media-template-for-an-entity"></a>Definiera mediamallen för en enhet

1.  Klicka på **Butik** &gt; **Kataloghantering** &gt; **Katalogbilder**.
2.  På **Katalogbilder** sidan i åtgärdsfönstret klickar du på **Definiera mediammall**. I **Definiera mediamall** dialogrutan i **Enhet** fältet, **Katalog** ska markeras som standard.
3.  På **Mediesökväg** snabbfliken anger du den återstående sökvägen till bildplatsen. Mediesökvägen stöder **LanguageID** som en variabel. Till exempel för demonstrationsdata kan du skapa en **Kataloger** mapp för alla katalogbilder under mediabas-URL för din mediaserver (https://testax3ret.cloud.test.dynamics.com/RetailServer/MediaServer). Du kan sedan ha en mapp för varje språk, till exempel en-US eller fr-FR och kopiering lämpliga bilderna under varje mapp. Om du inte har olika bilder för olika språk, kan du utesluta **LanguageID** variabeln i din mappstruktur, och peka direkt till katalogmappen, som innehåller katalogbilder. **Notering:** Den aktuella versionen av Dynamics 365 for Retail stöder **{LanguageId}** token för katalog-, produkt- och kategorienheter. (**{LanguageID}** token stöds inte för kund- och arbetarenheter, enligt den befintliga standard som har varit gällande sedan Microsoft Dynamics AX 6.x.)
4.  För bilder, filnamnformatet är hårdkodat till katalognamnet och kan inte ändras. Byt namn på dina bilder, så att de har rätt katalognamn, för att garantera att MPOS hanterar dem korrekt.
5.  I **Filtillägg** fältet, välj det förväntade filnamnstillägget, beroende på vilken typ av bilder som du har. Till exempel för demodata har katalogbilder ställts in .jpg filtillägget. (Bildfiler byter också namn så att de har katalognamn).
6.  Klicka på **OK**.
7.  För att validera att mediamallen för bilder har sparats korrekt, på sidan **Katalogbilder**, klicka på nytt på **Definiera mediamallen**. Om du vill validera mallen, utan att stänga **Definiera mediamallen** dialogrutan kan du använda **Generera bild-URL för Excel** snabbfliken. Kontrollera utseendet på bild-URL och kontrollera att URL överensstämmer med mallstandarden som nämndes tidigare. **Definiera mediamallen** dialogrutan har nu angett bildsökvägen obetingat för alla katalogbilder som använder den vanliga URL-sökvägen. Den här URL-sökvägen gäller för alla katalogbilder, om de inte skrivs över. Den första delen av bildsökvägen hämtas från mediabas-URL som du har definierat i kanalprofilen. Resterande del av sökvägen hämtas från den sökväg som du har definierat i mediamallen. De två delarna sammanfogas för att ge fullständig URL till bildplatsen. Till exempel en katalog i demodata kallas Fabrikam baskatalogen. Därför måste bildnamnet vara Fabrikam Base Catalog.jpg, så att den använder det katalognamn och .jpg filnamnstillägg som konfigureras i mallen. I det här fallet, efter sammanfogning, kommer URL vara https://testax3ret.cloud.test.dynamics.com/RetailServer/MediaServer/Catalogs/en-US/Fabrikam Base Catalog.jpg.
8.  Kör synkroniseringjobben för att flytta den nya mallen till kanaldatabasen, så att MPOS kan använda mallen för åtkomst till bilderna.
9.  Uppdatera mediamallen för katalogbilder på kanalsidan, kontrollera att du kör **Katalogjobb 1150** från **Butik-IT** &gt; **Distributionsschema**.[![katalog1](./media/catalog1.png)](./media/catalog1.png)

## <a name="previewing-an-image-from-the-entity-level"></a>Granska en bild ur enhetsnivå
1.  Från sidan för enhetsartikeln i HQ kan du granska den bild som använder bild-URL, som härleds från mediamallen. För det här exemplet, gå till lämplig katalog, och sedan, i åtgärdsfönstret, klicka på **Media** &gt; **Bilder**. Använd listrutan om du vill välja olika butiker som kan ha olika kanalprofiler.
2.  Om du vill redigera eller ta bort den implicita mediamallen måste du gå tillbaka till **Definiera mediamall** dialogrutan för **Katalogbilder** sidan.
3.  Du kan använda **Lägg till** och **Ta bort** knapparna som manuellt ändrar sökvägen baserat på den implicita mallen och använda för en viss bild. Mer information finns i ”Skriva över mediamallen för enhetsartiklar" senare i denna artikel.
4.  När du är klar att granska en bild och med de ändringar som du behöver, starta MPOS-instansen för den aktuella butiken och se om katalogbilderna visas.[![katalog4](./media/catalog4.png)](./media/catalog4.png)

**Notering:** Du kan använda samma procedur för alla fem enheter som stöds: Arbetare, kund, katalog, kategori och produkter. ”Katalogprodukter” (produkter som anges på katalognivån), och " kanalprodukter " (produkter som anges på kanalnivån) använder mediamallen som anges för produktenheten. För produktmediamallen kan du välja antalet produktbilder som du vill visa per produkt. Du kan även ange standardbilden för en viss produkt. På så sätt kan du förebygga tomma bilder i MPOS och få hjälp att kontrollera vilken bilden som används som standardbild för en produktartikel. I följande exempel har varje produkt fem bilder, och den första bilden anges som standardbilden. Variantprodukter hanteras på samma sätt som huvudplaneringsprodukter. Filnamnet på bildfilen ska baseras på produktnumret. Vissa tecken undantas också medan filnamnet genereras. Därför är det bra att verifiera filnamnet genom att använda **Generera bild-URL för Excel** avsnittet. [![prods](./media/prods.png)](./media/prods.png)  

## <a name="synchronization-jobs-to-send-a-media-template-to-the-channel-side"></a>Synkroniseringsjobb för att skicka en mediamall till kanalsidan
För alla fem enheter som stöds (arbetare, kund, katalog, kategori och produkter), när du uppdaterar dialogrutan **Definiera mediamallen** m du vill ställa in en bild, se till att du kör katalogjobbet (1150 ) från **Butik-IT** &gt; **Distributionsschema**. Detta jobb ska aktivera den uppdaterade mediamallen som ska synkroniseras med kanalen och användas av MPOS. Kör katalogjobbet (1150 )när du gjort någon av följande ändringar:

-   Du uppdaterar katalogbildmediamallen från **Katalogbilder** &gt; **Definiera mediamall**.
-   Du uppdaterar medarbetarbildmediamallen från **Medarbetarbilder** &gt; **Definiera mediamall**.
-   Du uppdaterar kundbildmediamallen från **Kundbild** &gt; **Definiera mediamall**.
-   Du uppdaterar produktbildmediamallen från **Produktbilder** &gt; **Definiera mediamall**.
-   Du uppdaterar kategoribildmediamallen från **Kategoribilder** &gt; **Definiera mediamall**. Du måste även publicera kanalen.

## <a name="overwriting-the-media-template-for-entity-items"></a>Skriva över mediummallen för enhetsartiklar
Som du lärde dig i det föregående avsnittet, stöder mediamallen för en viss enhet bara en gemensam sökväg. Den sökvägen baseras på mediabas-URL, som konfigureras, och mediasökvägen som definieras. Men i många fall vill en återförsäljare kunna använda bilder från andra källor för en delmängd artiklar i en enhet. Till exempel en butik använder sin värdmediaserver för en uppsättning katalogbilder men använder CDN-URL för en annan uppsättning. Om du vill skriva över bild-URL, som baseras på en mediamall för enhetsbilder på enhetsnivå, kan du använda Redigera i Excel och Manuell redigering från sidan **Förhandsgranska**.

### <a name="overwrite-by-using-edit-in-excel"></a>Skriv över genom att använda Redigera i Excel

1.  Klicka på **Butik** &gt; **Kataloghantering** &gt; **Katalogbilder**.
2.  På **Katalogbilder** sidan klickar du på **Definiera mediamall**. I **Definiera mediamall** dialogrutan i **Enhet** fältet ska **Katalog** markeras.
3.  På **Mediesökväg** snabbfliken, notera bildplatsen.
4.  Klicka på **Generera** på snabbfliken **Generera bild-URL för Excel**. **Viktigt:** Så snart mediamallen ändras, måste du klicka på **Generera** innan du kan använda Redigera i Excel-funktionen. [![excel1](./media/excel1.jpg)](./media/excel1.jpg) Du ser nu en förhandsgranskning av bild-webbadresserna som har genererats utifrån den senast sparade mediamallen. [![excel2](./media/excel2.png)](./media/excel2.png) **Obs!** De webbadresser som genereras för Excel använder sökvägen och konventionerna i den definierade mediamallen. Dessa inkluderar konventioner för filnamn. Förväntan är att du har ställt in de fysiska bilderna utanför Dynamics 365 for Retail och bilderna kan hämtas från URL som härleds från mediamallen, som du tidigare definierade. Du kan skriva över härledda URL genom att använda Redigera i Excel-funktionen.
5.  Klicka på **Redigera i Excel**.
6.  Klicka på **Aktivera redigeringen** när du uppmanas, efter att Microsoft Excel kalkylbladet har öppnats.
7.  Klicka på i högra fönstret **Har förtroende här tilläggsprogram** och väntar på tilläggsprogrammet för att slutföra installationen, när du uppmanas. [![Lita på det här tillägget](./media/excel4.jpg)](./media/excel4.jpg)
8.  Om du uppmanas att logga in, anger du den inloggningsinformation som du använde för att logga in på huvudkontoret. [![Inloggningsuppmaning](./media/excel5.png)](./media/excel5.png)
9.  När du har signerat in, ska du vara en stånd till att visa listan över bildURL för de olika av katalogposterna.
10. Du lägger till, redigera och ta bort bildURL för olika enhetartiklar.
11. För alla enheter utom produkter kan du skriva över bildURL. Ändra befintlig bildURL, så att den använder den nya målURL av bilden, uppdatera och filnamn med den nya filnamn för den bildfil. Filnamnet måste vara unikt att garantera att posten är unikt. [![Skriv över bild-URL:er i Excel](./media/excel6.jpg)](./media/excel6.jpg) **Obs!** När du skriver över bild-URL:er för produktenheter, genom att använda Redigera i Excel-funktionen eller enhetartikelsidan, visar alltid MPOS alla bild-URL:er för mediamallar tillsammans med de överskriva bild-URL:erna.
12. När du är klar med ändringarna, klickar **Publicera i Excel** du på du vill skapa en ny stötande associationpost.
13. Återgå till Huvudkontor och klicka **OK** på.
14. Kör lämpliga synkroniseringjobben för enheten och kontrollera förhandsgranskning på enhetsidan eller i MPOS.

#### <a name="creating-new-records"></a>Skapa nya registreringar

Du kan skapa nya poster i Excel. Se därför till att du använder rätt information. Kontrollera att katalogen, användar-ID och katalognamn är korrekt, och även vill ange en unik filnamn, till exempel vill skapa en ny post för en katalog. Den unika filnamn är mycket viktig, eftersom unikheten över poster i Excel ska valideras under publicering. Första kopiera information från mappen som du vill skapa en ny post för och kopiering posten. Du måste uppdatera bara filnamn och URL, eftersom resten av informationen ska vara identiska. Om du vill skapa nya poster för produktenhetartiklar du använder samma grundläggande proceduren. Kopiera en befintlig post för produkten som du skapar en ny post för och sedan som ersätter det bild URL och filnamnet i Excel-kalkylbladet. Kontrollera att filnamn är unikt.

#### <a name="deleting-an-existing-record"></a>Ta bort en befintlig post

Endast de överskrivavna bildURLposterna tas bort. När en bild har tagits bort, och synkronisering ska utföras, bilden visas inte längre på **Förhandsgranska** sidan eller i MPOS. BildURLposter, som härleds från mediummallen, kan inte tas bort, eftersom dessa poster alltid härleds från mediummallen varje gång.

### <a name="overwrite-from-the-entity-level-preview-page"></a>Skriv över från enhetsnivå sidan Förhandsgranska

För alla enheter utom produkter kan du skriva över bildURL för en viss enhetartikel på enhetartikelnivån från sidan **Förhandsgranska**. För produkter kan du använda sidan ”katalogprodukt" enhet. Det här exemplet visar hur du ersätter en katalogbild.

1.  Klicka på **Kataloger** &gt; **Media** &gt; **Bilder** och välje katalogbilden som ska uppdateras.
2.  Klicka **Lägg till** på, och anger bildURL om du vill skriva över mediummallURL.
3.  Om du vill att den här bild ska visas i MPOS för katalogen, kan du ange den som standardinställningbilden.
4.  Klicka på **OK**. BildURL uppdateras för den här katalogbild, och en förhandsgranskning visas. [![förhandsgranskning3](./media/preview3.png)](./media/preview3.png)
5.  Du kan även se bildförtitten för alla överskrivavna bildURL på gallerisidan **Katalogbilder**.

**[![förhandsgranskning-4](./media/preview-4.png)](./media/preview-4.png)Obs!** För närvarande visas galleriet inte bildförtittar för URL för medium mallbild. För katalog-, arbetare-, kund och kategorienheter om användaren innehåller tydligt en URL via den här sidan, rekommenderar vi att du anger vilken bild är standardinställningbilden, eftersom Retail serverklienter visar bara en bild per katalog, kund, anställd och kategori. Om användaren inte anger en standardinställningbild, bestämmer systemet standardinställningbilden och skicka den till Retail Chain Manager-menyn uppringangen tjänst (MPOS eller ecommercen).

### <a name="overwrite-the-image-url-for-catalog-product-images-from-the-preview-page"></a>Skriv över bildURL för katalogproduktbilder från förtittsidan

Om du vill skriva över bildURL för katalogproduktbilder måste du använda sidan **Förhandsgranska**. Du kan inte använda funktionerna i Redigera i Excel.

1.  Välj en katalog och välj produkten att skriva över bilden för att skriva över produktbilder på en katalognivå.
2.  Klicka på **Attribut**.
3.  På nästa sida markera **Bild** och klicka på **Redigera**. Sidan **Preview** öppnar en dialogruta med skjutreglage.
4.  Klicka **Lägg till** på, och skriver över bildURL med en ny URL-adressen.
5.  Klicka på **OK**. Du ser förhandsgranskning av den och välj den kan nu ange den som standardinställningbilden.

**[![kat3](./media/cat3.png)](./media/cat3.png)Obs!** När du har kategoribildassociation, måste du publicera kanalen och köra kanaljobbet att garantera att ändringarna publiceras på kanaldatabasen.

## <a name="setting-up-images-to-appear-in-offline-mode-for-mpos"></a>Ställa in bilder som anges i fältet offline läget för MPOS
MPOS kan det i läget OLAP-kuber (när MPOS som är försäljningen i minut server) eller offline det läget (när det inte finns någon Retail server eller nätverksanslutning, och transaktioner lagras i en lokal offlinedatabas). När MPOS körs i frånkopplat läge, kan den inte få bilder från extern bildserveren om du vill visa från ett lämpligt servern, eftersom Retail servermöjlighet anslutning har förlorats. Du kan dock fortfarande ställa in bilder, så att de visas, när MPOS körs i frånkopplat läge.

### <a name="set-up-product-images-to-appear-in-offline-mode-for-mpos"></a>Ställ in produktbilder som anges i fältet offline läget för MPOS

Produktbilderna, som måste användas i frånkopplat leveranssätt, kan ställas in, genom att överföra den begärda fysiska till bilden basproduktbilden.

1.  Klicka på **Produktinformationshantering** &gt; **Produkter** &gt; **Produkter**.
2.  Välj produkten att ange den offline bilden för.
3.  Klicka **Redigera** på, och sedan klicka på pilen i högra hörnet för att visa det högra fönstret.
4.  I **Produktbild** snabbfliken överför **Ändra bild** på, och den fysiska bilden som ska användas för den valda produkten i frånkopplat läge.
5.  Spara och stäng formuläret
6.  Kör katalogjobbet i Huvudkontor, medan att se till MPOS är anslutet i form, att data skickas minst en gång till offlinedatabasen.
7.  Sätt MPOS till frånkopplat läge. Du bör se den bild du överför för den specifika Huvudkontor i produkten. [![offline1](./media/offline1.png)](./media/offline1.png)

 

### <a name="set-up-catalog-category-employee-and-customer-images-to-appear-in-offline-mode-for-mpos"></a>Ställ in katalogen, kategori, medarbetare och kundbilder som ska visas i det läget för MPOS offline

Katalogen, kategori, medarbetare och kundbilderna, som måste användas i frånkopplat leveranssätt, kan ställas in, genom att lägga till den begärda bildens mållänken till gallerit och ange bilden som standardinställningbilden för den valda enheten.

1.  Gå till katalogen och sedan, i åtgärdsfönstret, klicka på **Media** &gt; **Bilder**.
2.  Följ stegen i **Skriv över från enhet-nivån förtittsidan** om du vill lägga till den externa bildURL.
3.  Välj den bild, som standardinställningbilden för katalogen, genom att markera kryssrutan mot bilden, angav i rutnätet.
4.  Kör katalogjobbet. Den bild du vill använda nu som den offline bilden för den katalog i MPOS.
5.  Följ en liknande process för andra enheter, till exempel kategori, medarbetare och kund.

[![offline2](./media/offline2.png)](./media/offline2.png)    




