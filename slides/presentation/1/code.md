# Exemple : E2E - Renovation 
```ts {all|2|3|4|7|8|9|all}{maxHeight:'440px'}
// renovation.spec.ts
test.beforeEach(async ({ authentication, scenario }) => {
	await authentication.signIn();
	await scenario.createScenario();
});

test("(➕) Add a renovation", async ({ page }) => {
	await page.goto("/numerical-twins/5/scenarios");
	await page.getByRole("button", { name: "playwright-generated-" }).getByRole("link").first().click();
	await page.getByRole("button", { name: "Planifier" }).first().click();
	await page.getByPlaceholder("€").click();
	await page.getByPlaceholder("€").fill("123");
	await page.getByPlaceholder("Ajouter une description plus").click();
	await page.getByPlaceholder("Ajouter une description plus").fill("Playwright-generated-description");
	await page.getByRole("button", { name: "Valider" }).click();
});

test("(➖) Delete a renovation", async ({ page }) => {
	await page.getByRole("link", { name: "Planification beta" }).click();
	await page.getByText("2025").click();
	await page.locator("header").getByRole("button").first().click();
	await page.getByRole("button", { name: "Supprimer" }).click();
});

test.afterEach(async ({ scenario, authentication }) => {
	await scenario.remove();
	await authentication.logout();
});
```