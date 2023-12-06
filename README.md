productscreen
This Project is Product Screening, For adding, updating, filtering, deleting and approving or rejecting products. Having these services:

API to List Active Products:

Endpoint: GET /api/products
Description: Get the list of active products sorted by the latest first.
API to Search Products:

Endpoint: GET /api/products/search
Parameters: productName (optional), minPrice (optional), maxPrice (optional), minPostedDate (optional), maxPostedDate (optional)
Description: Search for products based on the given criteria (product name, price range, and posted date range).
API to Create a Product:

Endpoint: POST /api/products
Request Body: Product object (name, price, status)
Description: Create a new product, but the price must not exceed $10,000. If the price is more than $5,000, the product should be pushed to the approval queue.
API to Update a Product:

Endpoint: PUT /api/products/{productId}
Request Body: Product object (name, price, status)
Description: Update an existing product, but if the price is more than 50% of its previous price, the product should be pushed to the approval queue.
API to Delete a Product:

Endpoint: DELETE /api/products/{productId}
Description: Delete a product, and it should be pushed to the approval queue.
API to Get Products in Approval Queue:

Endpoint: GET /api/products/approval-queue
Description: Get all the products in the approval queue, sorted by request date (earliest first).
API to Approve a Product:

Endpoint: PUT /api/products/approval-queue/{approvalId}/approve
Description: Approve a product from the approval queue. The product state should be updated, and it should no longer appear in the approval queue.
API to Reject a Product:

Endpoint: PUT /api/products/approval-queue/{approvalId}/reject
Description: Reject a product from the approval queue. The product state should remain the same, and it should no longer appear in the approval queue.
Status is mentioned with PENDING(1), APPROVED(2), REJECTED(3)

Having the swagger ui for testing the API services: http://localhost:8080/swagger-ui.html
