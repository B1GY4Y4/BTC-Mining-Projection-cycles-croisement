Données hashrate & prix (blockchain.com) — Dernier point disponible : 17/06/2026 (3 jours).
Données récentes — aucune action requise. Télécharger un nouveau JSON ↗ puis relancer le générateur.
📐 Règles de construction du graphique
1. Sources de données
Prix BTC (fenêtre glissante) : export CSV quotidien Bitcoin_Données_Historiques.csv — couvre 2010 → aujourd'hui
Hashrate réseau (calibration) : export JSON hash-rate.json depuis blockchain.com/explorer/charts/hash-rate — dernière mise à jour : 17/06/2026
2. Fenêtre glissante des prix
Les 1 458 jours précédant aujourd'hui (24/06/2022 → 20/06/2026) sont rejoués vers l'avenir (principe bitbo.io/cycle-repeat). La morphologie projetée hérite de la forme réelle du marché — corrections brutales, faux tops, rebonds — sans anchors arbitraires.

3. Amortissement progressif (texture)
Chaque variation quotidienne est comprimée non-linéairement : v_amorti = signe(v) × |v|^(1+(1−facteur)). Les grands mouvements (±10%) sont plus comprimés que les petits (±0.5%). La direction et la texture restent intactes.

4. Rescaling vers tops cibles
Après amortissement, la courbe est rescalée en log pour atteindre exactement le top cible. Top précédent de référence : $126 000 (octobre 2025).

Scénario	Ratio top/top préc.	Top cycle 1	Amort. quotidien	Élasticité HR
🐻 Bear	×1.50	$189 000	0.65	0.30
⚖ Base	×1.80	$226 800	0.75	0.50
🐂 Bull	×2.50	$315 000	0.85	0.70
5. Modèle hashrate (calibré sur données blockchain.com)
Calibration sur 3 cycles historiques (2016-2020, 2020-2024, 2024-2026) :

Lag retenu : 270 jours — corrélation prix→hashrate maximale observée empiriquement
Élasticité : 0.29 observé cycle 2020-2024 (très industrialisé), 0.54 cycle 2024-2026 → plage 0.30–0.70 selon scénario
Plancher +3%/an : amélioration ASICs + nouveaux entrants, indépendant du prix
Choc halving −5% / 56j : atténué vs cycles précédents, les miners industriels anticipent désormais
Formule : HR = max(HR_ref × (px_lag270j/px_today)^élasticité, HR_ref × 1.03^(j/365))

6. Calcul du BTC net journalier
PR : sat/TH/j = BTC_émis × 1e8 / (hashrate_EH × 1e6)
Frais : (0.05×24×EE/1000 + 0.0089) × (1−remise) / prix_BTC
Net : MAX(0, PR/1e8 − frais) × TH × (1 + superperf_Wars)
BTC émis : 450/j → 225/j (avr 2028) → 112.5/j (avr 2032)
Mécanisme clé : frais en USD fixes, payés en BTC → quand le BTC monte, les frais en BTC s'effondrent et le net explose de façon supra-linéaire
7. Croisement
Le point ★ indique le premier jour où le BTC miné cumulé dépasse la cible spot : quantité de BTC qu'on aurait obtenu en achetant spot à chaque date d'achat de miner, figée à 0.34917517 BTC.

8. Limites du modèle
La répétition de la fenêtre glissante suppose une récurrence des cycles — invalidable par les ETF institutionnels, l'adoption des États ou des chocs macro
La superperformance Wars est supposée constante — elle varie selon la ligue, le clan et les cycles Miner Wars
Les frais GoMining sont supposés stables — la structure tarifaire peut évoluer
Ce graphique est un simulateur de scénarios, pas une prévision
