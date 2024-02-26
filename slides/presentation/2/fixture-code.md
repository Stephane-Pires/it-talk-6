# Exemple : Fixture
```ts {all}{maxHeight:'440px'}
// Scenario.ts
import { expect, type Page } from "@playwright/test";

export class Scenario {
	private id: string | null = null;

	constructor(public readonly page: Page) {	}

	async create() {
		await this.page.goto("/numerical-twins/5/visualization");
		await this.page.waitForTimeout(1500);
		await this.page.getByTestId("input-name-scenario").fill("playwright-generated-scenario");
		await this.page.getByTestId("save-scenario").click();

		const toastId = await this.page.getByTestId(RegExp(/toast-scenario-saved-id-\d+/));
		await expect(toastId).toHaveAttribute("id", { timeout: 40000 });
		await toastId.getAttribute("id").then((id) => {
			this.id = id;
		});
	}

	async remove(id: string | null = this.id) {
		await this.page.goto("/numerical-twins/5/scenarios");

		await this.page.getByTestId(`scenario-delete-${id}`).click();
	}
}
```