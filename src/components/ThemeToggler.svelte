<script>
    import {onMount} from "svelte";
    let currentTheme;
    onMount(() => {
        applyTheme();
        window.matchMedia(DARK_PREFERENCE).addEventListener('change', applyTheme);
    });

	const STORAGE_KEY = 'theme';
	const DARK_PREFERENCE = '(prefers-color-scheme: dark)';

	const THEMES = {
		DARK: 'dark',
		LIGHT: 'light'
	};

	const prefersDarkThemes = () => window.matchMedia(DARK_PREFERENCE).matches;

	const toggleTheme = () => {
		const stored = localStorage.getItem(STORAGE_KEY);

		if (stored) {
			localStorage.removeItem(STORAGE_KEY);
		} else {
			localStorage.setItem(STORAGE_KEY, prefersDarkThemes() ? THEMES.LIGHT : THEMES.DARK);
		}

		applyTheme();
	};
	const applyTheme = () => {
		const preferredTheme = prefersDarkThemes() ? THEMES.DARK : THEMES.LIGHT;
		currentTheme = localStorage.getItem(STORAGE_KEY) ?? preferredTheme;

		if (currentTheme === THEMES.DARK) {
			document.documentElement.classList.remove(THEMES.LIGHT);
			document.documentElement.classList.add(THEMES.DARK);
		} else {
			document.documentElement.classList.remove(THEMES.DARK);
			document.documentElement.classList.add(THEMES.LIGHT);
		}
	};
</script>

<input type="checkbox" checked={currentTheme !== THEMES.DARK} on:click={toggleTheme} />
