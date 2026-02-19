# mozai.github.io
/* ============================================
   MOZAÏ - Site Web
   style.css - Feuille de style globale
   ============================================ */

/* --- Reset & Base --- */
*, *::before, *::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
  font-size: 16px;
}

body {
  font-family: 'Segoe UI', 'Helvetica Neue', Arial, sans-serif;
  color: #1A1A1A;
  background-color: #FFFFFF;
  line-height: 1.7;
}

a {
  text-decoration: none;
  color: inherit;
  transition: color 0.3s ease;
}

ul {
  list-style: none;
}

img {
  max-width: 100%;
  height: auto;
  display: block;
}

/* --- Variables couleurs --- */
:root {
  --magenta: #E5007D;
  --jaune: #FFD100;
  --violet: #8B1F8E;
  --noir: #1A1A1A;
  --blanc: #FFFFFF;
  --gris-clair: #F5F5F5;
  --gris-moyen: #E0E0E0;
  --gris-texte: #555555;
  --transition: 0.3s ease;
}

/* --- Typographie --- */
h1, h2, h3, h4 {
  font-weight: 700;
  line-height: 1.3;
  color: var(--noir);
}

h1 {
  font-size: 2.8rem;
  margin-bottom: 1rem;
}

h2 {
  font-size: 2rem;
  margin-bottom: 1.5rem;
  text-align: center;
}

h3 {
  font-size: 1.4rem;
  margin-bottom: 1rem;
}

p {
  margin-bottom: 1rem;
  color: var(--gris-texte);
}

/* --- Container --- */
.container {
  max-width: 1140px;
  margin: 0 auto;
  padding: 0 20px;
}

/* --- Section --- */
.section {
  padding: 80px 0;
}

.section--grey {
  background-color: var(--gris-clair);
}

.section-subtitle {
  text-align: center;
  color: var(--gris-texte);
  max-width: 700px;
  margin: -1rem auto 3rem auto;
  font-size: 1.1rem;
}

/* ============================================
   NAVIGATION
   ============================================ */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background: var(--blanc);
  box-shadow: 0 2px 10px rgba(0,0,0,0.08);
  z-index: 1000;
  padding: 0 20px;
}

.navbar .container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 70px;
}

.navbar__logo {
  display: flex;
  align-items: center;
  gap: 10px;
  font-size: 1.5rem;
  font-weight: 700;
  letter-spacing: 3px;
  color: var(--noir);
}

.navbar__logo img {
  height: 40px;
  width: auto;
}

.navbar__menu {
  display: flex;
  align-items: center;
  gap: 30px;
}

.navbar__link {
  font-size: 0.95rem;
  font-weight: 500;
  color: var(--noir);
  position: relative;
  padding: 5px 0;
}

.navbar__link::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background: var(--magenta);
  transition: width var(--transition);
}

.navbar__link:hover::after,
.navbar__link--active::after {
  width: 100%;
}

.navbar__link:hover {
  color: var(--magenta);
}

.navbar__cta {
  background: var(--magenta);
  color: var(--blanc);
  padding: 10px 24px;
  border-radius: 30px;
  font-weight: 600;
  font-size: 0.9rem;
  transition: background var(--transition), transform var(--transition);
}

.navbar__cta:hover {
  background: var(--violet);
  transform: translateY(-2px);
}

/* Hamburger (mobile) */
.navbar__toggle {
  display: none;
  flex-direction: column;
  gap: 5px;
  cursor: pointer;
  background: none;
  border: none;
  padding: 5px;
}

.navbar__toggle span {
  display: block;
  width: 25px;
  height: 3px;
  background: var(--noir);
  border-radius: 3px;
  transition: var(--transition);
}

/* ============================================
   HERO
   ============================================ */
.hero {
  margin-top: 70px;
  background: linear-gradient(135deg, #1A1A1A 0%, #2D0A3E 50%, #1A1A1A 100%);
  color: var(--blanc);
  padding: 100px 0;
  text-align: center;
  position: relative;
  overflow: hidden;
}

.hero::before {
  content: '';
  position: absolute;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background: radial-gradient(circle at 30% 50%, rgba(229,0,125,0.15) 0%, transparent 50%),
              radial-gradient(circle at 70% 50%, rgba(139,31,142,0.1) 0%, transparent 50%);
  animation: heroGlow 8s ease-in-out infinite alternate;
}

@keyframes heroGlow {
  0% { transform: scale(1) rotate(0deg); }
  100% { transform: scale(1.1) rotate(5deg); }
}

.hero__content {
  position: relative;
  z-index: 1;
  max-width: 800px;
  margin: 0 auto;
}

.hero h1 {
  color: var(--blanc);
  font-size: 3rem;
  margin-bottom: 0.5rem;
}

.hero__highlight {
  color: var(--magenta);
}

.hero__tagline {
  font-size: 1.3rem;
  color: rgba(255,255,255,0.85);
  margin-bottom: 2rem;
  font-weight: 300;
}

.hero__description {
  font-size: 1.05rem;
  color: rgba(255,255,255,0.7);
  margin-bottom: 2.5rem;
  line-height: 1.8;
}

.hero__buttons {
  display: flex;
  gap: 15px;
  justify-content: center;
  flex-wrap: wrap;
}

/* --- Boutons globaux --- */
.btn {
  display: inline-block;
  padding: 14px 32px;
  border-radius: 30px;
  font-weight: 600;
  font-size: 1rem;
  cursor: pointer;
  transition: all var(--transition);
  border: none;
  text-align: center;
}

.btn--primary {
  background: var(--magenta);
  color: var(--blanc);
}

.btn--primary:hover {
  background: var(--violet);
  transform: translateY(-3px);
  box-shadow: 0 8px 25px rgba(229,0,125,0.3);
}

.btn--outline {
  background: transparent;
  color: var(--blanc);
  border: 2px solid var(--blanc);
}

.btn--outline:hover {
  background: var(--blanc);
  color: var(--noir);
  transform: translateY(-3px);
}

.btn--outline-dark {
  background: transparent;
  color: var(--magenta);
  border: 2px solid var(--magenta);
}

.btn--outline-dark:hover {
  background: var(--magenta);
  color: var(--blanc);
  transform: translateY(-3px);
}

/* ============================================
   CARDS - Services
   ============================================ */
.services-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 30px;
  margin-top: 2rem;
}

.service-card {
  background: var(--blanc);
  border-radius: 16px;
  padding: 40px 30px;
  text-align: center;
  box-shadow: 0 4px 20px rgba(0,0,0,0.06);
  transition: transform var(--transition), box-shadow var(--transition);
  border-top: 4px solid transparent;
}

.service-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 12px 40px rgba(0,0,0,0.1);
}

.service-card:nth-child(1) {
  border-top-color: var(--magenta);
}

.service-card:nth-child(2) {
  border-top-color: var(--jaune);
}

.service-card:nth-child(3) {
  border-top-color: var(--violet);
}

.service-card__number {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  font-size: 1.2rem;
  font-weight: 700;
  color: var(--blanc);
  margin-bottom: 1.5rem;
}

.service-card:nth-child(1) .service-card__number {
  background: var(--magenta);
}

.service-card:nth-child(2) .service-card__number {
  background: var(--jaune);
  color: var(--noir);
}

.service-card:nth-child(3) .service-card__number {
  background: var(--violet);
}

.service-card h3 {
  font-size: 1.2rem;
  margin-bottom: 0.8rem;
}

.service-card p {
  font-size: 0.95rem;
}

.service-card__link {
  display: inline-block;
  margin-top: 1.5rem;
  color: var(--magenta);
  font-weight: 600;
  font-size: 0.95rem;
}

.service-card__link:hover {
  color: var(--violet);
}

/* ============================================
   STEPS (Comment procéder)
   ============================================ */
.steps {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  gap: 20px;
  flex-wrap: wrap;
  margin-top: 2rem;
}

.step {
  text-align: center;
  flex: 1;
  min-width: 200px;
  max-width: 300px;
}

.step__icon {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  background: var(--magenta);
  color: var(--blanc);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.8rem;
  font-weight: 700;
  margin: 0 auto 1rem auto;
}

.step__arrow {
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2rem;
  color: var(--magenta);
  padding-top: 25px;
}

/* ============================================
   QUOTE / Citation
   ============================================ */
.quote-block {
  background: linear-gradient(135deg, #2D0A3E, #1A1A1A);
  color: var(--blanc);
  padding: 60px 40px;
  border-radius: 16px;
  text-align: center;
  margin: 3rem 0;
  position: relative;
}

.quote-block__text {
  font-size: 1.15rem;
  font-style: italic;
  line-height: 1.8;
  color: rgba(255,255,255,0.9);
  max-width: 800px;
  margin: 0 auto 1.5rem auto;
}

.quote-block__text::before {
  content: '«';
  font-size: 3rem;
  color: var(--magenta);
  display: block;
  margin-bottom: 0.5rem;
}

.quote-block__author {
  font-weight: 700;
  font-size: 1.1rem;
  color: var(--jaune);
}

.quote-block__role {
  font-size: 0.9rem;
  color: rgba(255,255,255,0.6);
}

/* ============================================
   FEATURES LIST (➜ items)
   ============================================ */
.features-list {
  list-style: none;
  padding: 0;
}

.features-list li {
  padding: 12px 0 12px 35px;
  position: relative;
  font-size: 1.05rem;
  color: var(--gris-texte);
  border-bottom: 1px solid var(--gris-moyen);
}

.features-list li:last-child {
  border-bottom: none;
}

.features-list li::before {
  content: '➜';
  position: absolute;
  left: 0;
  color: var(--magenta);
  font-weight: 700;
}

/* ============================================
   STATS / Chiffres clés
   ============================================ */
.stats-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 30px;
  text-align: center;
  margin-top: 2rem;
}

.stat-card {
  background: var(--blanc);
  padding: 40px 20px;
  border-radius: 16px;
  box-shadow: 0 4px 20px rgba(0,0,0,0.06);
}

.stat-card__number {
  font-size: 2.5rem;
  font-weight: 800;
  color: var(--magenta);
  margin-bottom: 0.5rem;
}

.stat-card__label {
  font-size: 0.95rem;
  color: var(--gris-texte);
}

/* ============================================
   REFERENCES / Logos placeholder
   ============================================ */
.references-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 30px;
  align-items: center;
  justify-items: center;
  margin-top: 2rem;
}

.reference-placeholder {
  width: 150px;
  height: 80px;
  background: var(--gris-clair);
  border: 2px dashed var(--gris-moyen);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.8rem;
  color: #999;
  font-weight: 500;
}

/* ============================================
   SCOPES (Bilan Carbone)
   ============================================ */
.scopes-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 25px;
  margin-top: 2rem;
}

.scope-card {
  padding: 30px;
  border-radius: 16px;
  text-align: center;
  color: var(--blanc);
}

.scope-card:nth-child(1) {
  background: var(--magenta);
}

.scope-card:nth-child(2) {
  background: var(--violet);
}

.scope-card:nth-child(3) {
  background: linear-gradient(135deg, var(--magenta), var(--violet));
}

.scope-card h4 {
  color: var(--blanc);
  margin-bottom: 0.5rem;
  font-size: 1.1rem;
}

.scope-card p {
  color: rgba(255,255,255,0.85);
  font-size: 0.95rem;
}

/* ============================================
   TIMELINE (EU Green Deal)
   ============================================ */
.timeline {
  position: relative;
  max-width: 700px;
  margin: 2rem auto;
  padding-left: 40px;
}

.timeline::before {
  content: '';
  position: absolute;
  left: 15px;
  top: 0;
  bottom: 0;
  width: 3px;
  background: var(--magenta);
}

.timeline-item {
  position: relative;
  margin-bottom: 2rem;
  padding-left: 25px;
}

.timeline-item::before {
  content: '';
  position: absolute;
  left: -32px;
  top: 5px;
  width: 16px;
  height: 16px;
  border-radius: 50%;
  background: var(--magenta);
  border: 3px solid var(--blanc);
  box-shadow: 0 0 0 3px var(--magenta);
}

.timeline-item h4 {
  font-size: 1.1rem;
  margin-bottom: 0.3rem;
}

.timeline-item p {
  font-size: 0.95rem;
}

/* ============================================
   ABOUT (À propos)
   ============================================ */
.about-grid {
  display: grid;
  grid-template-columns: 1fr 2fr;
  gap: 50px;
  align-items: start;
}

.about-photo {
  width: 100%;
  max-width: 300px;
  height: 350px;
  background: var(--gris-clair);
  border-radius: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #999;
  font-size: 0.9rem;
  border: 2px dashed var(--gris-moyen);
}

.about-experience {
  margin-top: 2rem;
}

.about-experience h3 {
  color: var(--magenta);
  margin-bottom: 1rem;
}

/* ============================================
   CONTACT FORM
   ============================================ */
.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 50px;
}

.contact-info__item {
  display: flex;
  align-items: center;
  gap: 15px;
  margin-bottom: 1.5rem;
}

.contact-info__icon {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background: var(--magenta);
  color: var(--blanc);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.2rem;
  flex-shrink: 0;
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 6px;
}

.form-group label {
  font-weight: 600;
  font-size: 0.9rem;
  color: var(--noir);
}

.form-group input,
.form-group textarea,
.form-group select {
  padding: 14px 18px;
  border: 2px solid var(--gris-moyen);
  border-radius: 12px;
  font-size: 1rem;
  font-family: inherit;
  transition: border-color var(--transition);
  outline: none;
  background: var(--blanc);
}

.form-group input:focus,
.form-group textarea:focus,
.form-group select:focus {
  border-color: var(--magenta);
}

.form-group textarea {
  resize: vertical;
  min-height: 140px;
}

.btn--submit {
  background: var(--magenta);
  color: var(--blanc);
  padding: 16px 40px;
  border: none;
  border-radius: 30px;
  font-size: 1.05rem;
  font-weight: 700;
  cursor: pointer;
  transition: all var(--transition);
  align-self: flex-start;
}

.btn--submit:hover {
  background: var(--violet);
  transform: translateY(-3px);
  box-shadow: 0 8px 25px rgba(229,0,125,0.3);
}

/* ============================================
   FOOTER
   ============================================ */
.footer {
  background: var(--noir);
  color: rgba(255,255,255,0.7);
  padding: 50px 0 30px 0;
}

.footer__grid {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr;
  gap: 40px;
  margin-bottom: 2rem;
}

.footer__brand {
  font-size: 1.4rem;
  font-weight: 700;
  color: var(--blanc);
  letter-spacing: 3px;
  margin-bottom: 1rem;
}

.footer h4 {
  color: var(--blanc);
  margin-bottom: 1rem;
  font-size: 1rem;
}

.footer__links li {
  margin-bottom: 0.5rem;
}

.footer__links a:hover {
  color: var(--magenta);
}

.footer__bottom {
  border-top: 1px solid rgba(255,255,255,0.1);
  padding-top: 1.5rem;
  text-align: center;
  font-size: 0.85rem;
}

.footer__bottom a {
  color: var(--magenta);
}

/* ============================================
   RESPONSIVE
   ============================================ */
@media (max-width: 992px) {
  .services-grid,
  .scopes-grid {
    grid-template-columns: 1fr 1fr;
  }

  .about-grid {
    grid-template-columns: 1fr;
    text-align: center;
  }

  .about-photo {
    margin: 0 auto;
  }

  .footer__grid {
    grid-template-columns: 1fr 1fr;
  }
}

@media (max-width: 768px) {
  h1 { font-size: 2.2rem; }
  h2 { font-size: 1.6rem; }
  .hero { padding: 70px 0; }
  .hero h1 { font-size: 2.2rem; }
  .section { padding: 60px 0; }

  .navbar__menu {
    display: none;
    position: absolute;
    top: 70px;
    left: 0;
    width: 100%;
    background: var(--blanc);
    flex-direction: column;
    padding: 20px;
    gap: 15px;
    box-shadow: 0 4px 20px rgba(0,0,0,0.1);
  }

  .navbar__menu.active {
    display: flex;
  }

  .navbar__toggle {
    display: flex;
  }

  .services-grid,
  .scopes-grid {
    grid-template-columns: 1fr;
  }

  .contact-grid {
    grid-template-columns: 1fr;
  }

  .steps {
    flex-direction: column;
    align-items: center;
  }

  .step__arrow {
    transform: rotate(90deg);
    padding: 0;
  }

  .footer__grid {
    grid-template-columns: 1fr;
  }
}
