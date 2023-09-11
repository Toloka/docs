# Comparing variants

Finding the optimal variant (with good enough quality and low enough price) is the main goal of the tool. {{ llm-name }} shows all the created variants in one right-side column.

The first variant appears automatically in the **History** right-side area when you add a new class.

You can choose a metric to compare the resulting variants with each other. For a metric to be displayed you need to have a labeled dataset and run a model.

Changing prompt invalidates quality measurement for the variant you are currently editing. Changing dataset invalidates quality measurement for all variants.

After you modify the prompt or change the dataset, click **![Run test](_images/run-test.svg) Run test** to create a new variant.

The created variant will be displayed in the **History** area. You can compare the variant accuracy and price and select the best variants for your model.

When you have a variant with the best accuracy to price ratio (say, 85% accuracy to $4 per 1K items ratio is better than 88% accuracy to $9 per 1K items even though the accuracy is higher in the second variant), or the variant that fits you both in accuracy and price, [deploy the project](deploy.md) and use it with real datasets.

## Variant actions {#variant-actions}

The following actions are available for your variants:

- Sort the variants by accuracy or price using the **Sort by** option.

- Add a variant to favorite clicking ![Favorite](_images/favorite.svg). It will turn to ![Favorited](_images/favorite-orange.svg) and add the variant to the comparison in the table below. To remove the variant from the comparison, click ![Favorited](_images/favorite-orange.svg) once again.

- Delete a variant clicking ![Delete variant](_images/delete.svg).

    {% note info %}

    When there is only one variant it can't be deleted.

    {% endnote %}

## Next steps {#next-steps}

- [Deploy your project](deploy.md)