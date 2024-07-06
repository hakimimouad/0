// Fonction pour cliquer sur les boutons et divs avec les classes et éléments spécifiés
function clickButtons() {
    // Sélection des divs avec la classe "flex justify-end"
    const justifyEndDivs = document.querySelectorAll('.flex.justify-end');
    justifyEndDivs.forEach(div => {
        const button = div.querySelector('.btn.btn-sm.btn-outline');
        if (button) {
            button.click();
            console.log('Button clicked in justify-end div:', div);
        } else {
            console.log('Button not found in justify-end div:', div);
        }
    });

    // Sélection des divs avec la classe "flex items-center gap-1" contenant le texte "Next Lesson"
    const itemsCenterDivs = document.querySelectorAll('.flex.items-center.gap-1');
    itemsCenterDivs.forEach(div => {
        const textElement = div.querySelector('p');
        if (textElement && textElement.textContent.trim() === 'Next Lesson') {
            const spanElement = div.querySelector('span.w-[25px]');
            if (spanElement) {
                // Action à exécuter si le span est trouvé
                console.log('Span found in items-center div:', div);
                // Ajouter ici toute action supplémentaire que vous souhaitez exécuter sur le span
            } else {
                console.log('Span not found in items-center div:', div);
            }
        } else {
            console.log('Text "Next Lesson" not found in items-center div:', div);
        }
    });

    // Sélection des boutons avec la classe spécifiée et contenant les éléments internes
    const complexButtons = document.querySelectorAll('button.btn.relative.rounded-md.text-top.normal-case.opacity-90.disabled\\:bg-secondary.disabled\\:bg-opacity-50.disabled\\:text-secondary-content.hover\\:opacity-100.btn-secondary');
    complexButtons.forEach(button => {
        const innerDiv = button.querySelector('div.flex.items-center.gap-1');
        if (innerDiv) {
            const textElement = innerDiv.querySelector('p');
            const spanElement = innerDiv.querySelector('span.w-[25px]');
            if (textElement && textElement.textContent.trim() === 'Next Lesson' && spanElement) {
                button.click();
                console.log('Complex button clicked:', button);
            } else {
                console.log('Required elements not found in complex button:', button);
            }
        } else {
            console.log('Inner div not found in complex button:', button);
        }
    });

    // Sélection des divs avec la classe "flex items-center gap-1" contenant le texte "Next Lesson" (hors bouton)
    itemsCenterDivs.forEach(div => {
        const textElement = div.querySelector('p');
        if (textElement && textElement.textContent.trim() === 'Next Lesson') {
            const spanElement = div.querySelector('span.w-[25px]');
            if (spanElement) {
                console.log('Action performed on div with "Next Lesson" and span:', div);
                // Ajouter ici toute action supplémentaire que vous souhaitez exécuter sur le div
            } else {
                console.log('Span not found in items-center div:', div);
            }
        } else {
            console.log('Text "Next Lesson" not found in items-center div:', div);
        }
    });
}

// Appel de la fonction toutes les 5 secondes
setInterval(clickButtons, 5000);
