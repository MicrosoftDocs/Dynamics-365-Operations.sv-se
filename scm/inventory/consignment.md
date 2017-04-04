---
title: "Försändelse"
description: "Det här avsnittet beskriver hur du använder inkommande försändelselagerprocesser."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ConsignmentDraftReplenishmentOrderJournal, ConsignmentProductReceiptLines, ConsignmentReplenishmentOrder, ConsignmentVendorPortalOnHand, InventJournalOwnershipChange, InventOnHandItemListPage, PurchTable, PurchVendorPortalConfirmedOrders
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 220834
ms.assetid: 3c9d6de4-45d4-459a-aef7-0d9ad2c22b3a
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: d9dcdd63649d6dbff96efe2eec7cad34025ab2ee
ms.lasthandoff: 03/31/2017


---

# <a name="consignment"></a>Försändelse

Det här avsnittet beskriver hur du använder inkommande försändelselagerprocesser.

Försändelselagret är lager som ägs av en leverantör, men som lagras på din site. När du är klar att förbruka eller använda lagret, tar du över ägarskapet för lagret. Det här avsnittet innehåller information om hur du fysiskt leverantören ägs lagerbehållning utan att skapa redovisningstransaktioner, hur du startar en process där leverantören ägs lager kan reserveras fysiskt. Och hur du ändrar ägarskap för råmaterial för att kunna behandlas som en del av produktionen orderbehandling förbrukningen. Det finns också en del information om hur leverantörer kan övervaka förbrukning av deras lager genom att använda leverantörsamarbetesgränssnittet. Mer information om hur du aktiverar och konfigurerar inkommande försändelseprocesser finns i [Ställa in försändelse](set-up-consignment.md).

## <a name="overview-of-the-consignment-process"></a>Översikt över försändelseprocessen
I det här scenariot har exempelföretaget USMF ett försändelseavtal med leverantören US-104 för råmaterialet M9211CI.

1.  En order för försändelseåteranskaffning skapas manuellt av någon i USMF baserat på den förväntade efterfrågan. Ordern skapas för leverantören US-104 och en rad läggs till för artikel MS9211CI.
2.  Leverantören informeras om den förväntade leveransen. Detta kan utföras på ett av tre sätt:
    -   Alla som arbetar på USMF skickar orderinformation till leverantören.
    -   Leverantören kan övervaka den förväntade lagerbehållningen med hjälp av leverantörsamarbetesgränssnittet.
    -   Alla som arbetar på USMF filtrerar data på sidan **Lagerbehållning** för att endast visa posterna för leverantören US-104, där inleveransstatusen är **Beställd**och skickar sedan denna information till leverantören.

3.  Lagret levereras från US-104 till USMF.
4.  När materialet kommer till USMF, uppdateras försändelseåteranskaffningordern med en produktinleverans. Endast de fysiska kvantiteterna av det leverantörsägda lagret registreras. Det finns inga redovisningstransaktioner skapade, eftersom lagret fortfarande ägs av leverantören.
5.  Leverantören övervakar uppdateringar av den fysiska lagerbehållningen på sidan **Behållning i försändelselager**.
6.  Nu när det fysiska lagret finns reserverar produktionsprocessen det leverantörsägda lagret och startar produktionsordern för de färdiga varor som kommer att förbruka råmaterial M9211CI.
7.  Ägaren till det reserverade råmaterialet som ska förbrukas i dagens produktion ändras från US-104 till USMF. Detta görs med hjälp av en Journal för lagerägarskapsändring. Den här processen skapar inköpsorder där fältet **Ursprung** anges till **Försändelse**.
8.  Leverantören övervakar förbrukningen (ändring av ägarskap) på sidan **Mottagna produkter från försändelselager** och utfärdar en faktura baserat på avtalen mellan de två företagen.
9.  Produktionsprocessen förbrukar råmaterialet via en produktionsplocklista. Den fysiska reservationen uppdateras automatiskt efter att lagerbehållningen ägs av USMF.
10. Fakturan från US-104 bearbetas mot de inköpsorder som skapades automatiskt när journalen för lagerägarskapsändring bearbetades. Betalning görs till leverantören US-104 för det lager som förbrukades.

USMF utför ytterligare periodiska processer:

-   Den fysiska flyttningen av det leverantörsägda mellan olika lagerställen bearbetas med hjälp av en överföringsjournal.
-   Det fysiska lagret uppdateras med hjälp av journalen ** Artikelräkning **. Inventering kan också användas av leverantören för att uppdatera lagerbehållningen, om de har behörighet att göra detta.

Leverantören US-104, kan övervaka uppdateringarna på **Behållning i försändelselager**.

## <a name="consignment-replenishment-orders"></a>Order för försändelseåteranskaffning
En order för försändelseåteranskaffning är ett dokument som används för att begära och hålla ordning kvantiteterna av produkter, som en leverantör har för avsikt att leverera inom ett visst datumintervall genom att skapa beställda lagertransaktioner. Vanligtvis baseras detta på prognosen och faktisk efterfrågan av de specifika produkterna. Lagret som ska inlevereras mot ordern för försändelseåteranskaffning kvarstår leverantörens ägarskap. Endast innehav av produkter relaterade till uppdateringen av fysiska inleverans registreras och därför sker inga redovisningstransaktionsuppdateringar. Dimensionen**Ägare** används för att separat information om vilket lager som ägs av leverantören och som ägs av den mottagande juridiska personen. Försändelse påfyllnad orderrader har en **öppen order** status så länge hela kvantiteten av raderna inte har fått eller avbröts. När den fullständiga kvantiteten har tagits emot eller avbrutits, ändras status till **slutförd**. Den fysiska lagerbehållningen som gäller en order för försändelseåteranskaffning kan registreras med hjälp av en registreringsprocess samt en uppdateringsprocess för produktinleverans. Registreringen kan göras som en del av artikelinförselprocessen eller manuellt genom att uppdatera orderraderna. När uppdateringprocessen för produktinleverans används, görs en post i produktinleveransjournalen som kan användas för att bekräfta inleveranser av varor till leverantörerna. 

[![försändelse påfyllningsorder](./media/consignment-replenishment-order.png)](./media/consignment-replenishment-order.png)

## <a name="inventory-ownership-change-journal"></a>Journal för lagerägarskapsändring
Processen att ändra ägare för lagret från leverantören till mottagande juridisk person görs genom en Ändringsjournal för lageräganderätt. Inga förväntade lagertransaktioner skapas för journalen. De enda lagertransaktioner som skapas är de som relaterar till en bokförd journal. När journalen är bokförd:

-   Det leverantörsägda lagret sker med hjälp av **Äganderättändring**-referens med en **Såld**-status.
-   Lagerbehållning tas emot av den juridiska person som förbrukar den genom att använda en lagertransaktion som uppdaterats för produktinleveransen på inköpsordern. Detta ställer in orderns status på **Inlevererat**. Inköpsorder som används för försändelse har fältet **Ursprung** inställt på **Försändelse**.

Det går inte att uppdatera kvantiteten på rader för försändelseinköpsorder efter att ordern har skapats. 

[![ägande-ändra-lagerjournal](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)

## <a name="vendor-collaboration-in-consignment-processes"></a>Leverantörssamarbete i försändelseprocesser
Leverantörsamarbetesgränssnittet har tre sidor som är relaterade till den inkommande försändelseprocessen:

-   **Inköpsorder****förbrukar försändelse lagret** -visar detaljerad inköpsorderinformation berör ägarskap ändringen från processen försändelse.
-   **Mottagna produkter från försändelselager** - Visar information om de artiklar och kvantiteter som har produktinleveranser uppdaterade under ägandeskapets ändringsprocess.
-   **Behållning i försändelselager** - Visar information om försändelseartiklarna som de förväntas leverera och de artiklar som redan är fysiskt tillgängliga på kundsiten.


