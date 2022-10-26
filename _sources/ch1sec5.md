## Notion de temps de traitement et de traitement temps réel

Comme on pourra le constater par la suite, <span style="color:rgba(var(--pst-color-link),1)">**tous les traitements numériques des signaux sont basés sur une même opération de base qui est l'opération d'addition/multiplication (ou MAC = Multiplication Accumulation)**</span>. Le temps nécessaire à un traitement sera donc évalué en nombre d'addition/multiplication nécessaires. Un traitement est accompli en temps réel quand il délivre un échantillon de signal en sortie de traitement pour un échantillon de signal en entrée (c'est-à-dire à chaque période d'échantillonnage $T_e$).
    
