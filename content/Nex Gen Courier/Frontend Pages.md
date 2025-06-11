## Public Pages

1. **Tracking**
    
    - **UI Elements**:
        - Input for AWB/LR No.
        - "Track" button.
    - **Displayed Information**:
        - Current Location of the shipment.
        - Timestamp of the last update.
        - Detailed status description (e.g., "In Transit," "Out for Delivery").
        - A visual timeline or map illustrating the parcel's journey.
    - **Backend**: `public.trackShipment`
2. **Rate Calculator**
    
    - **UI Elements**:
        - Inputs for origin pincode, destination pincode, package weight (kg), and dimensions (length, breadth, height in cm).
        - "Calculate Rate" button.
    - **Displayed Information**:
        - A list of available carrier services with their estimated rates.
    - **Backend**: `public.calculateRate`

---

## Client Pages

1. **Signup**
    - **UI Elements**:
        - Inputs for Email, Mobile Number, Password, First & Last Name.
        - Inputs for KYC: Document Type, Document Number, File Uploads for documents.
        - "Sign Up" button.
    - **Backend**: `auth.signup`
2. **Login**
    - **UI Elements**:
        - Inputs for Email and Password.
        - "Login" button.
        - A "Forgot Password?" link.
    - **Backend**: `auth.login`
3. **Forgot Password**
    - **UI Elements**:
        - Input for registered email address.
        - "Send Password Reset Link" button.
    - **Backend**: `auth.forgotPassword`
4. **User Profile**
    - **UI Elements**:
        - Display of current profile information (Name, Email, Mobile, Address).
        - Display of KYC status (Pending, Approved, Rejected).
        - Editable fields to update profile details.
        - "Update Profile" button.
    - **Backend**: `user.getProfile` to fetch data, `user.updateProfile` to save changes.
5. **Wallet Recharge**
    - **UI Elements**:
        - Input for the amount to add.
        - Selection of payment gateway (e.g., Razorpay, Stripe).
        - "Add Funds to Wallet" button, which proceeds to the payment gateway.
    - **Backend**: `wallet.initiateRecharge`
6. **Wallet Passbook**
    - **UI Elements**:
        - A table view of all wallet transactions (credits and debits).
        - Columns: Date, Description, Amount, Transaction Type, Status.
        - Filters for date range and transaction type.
        - "Export to Excel" button.
    - **Backend**: `wallet.getPassbook` to fetch history, `reports.getWalletData` for export.
7. **Order Booking (Single & Bulk)**
    - **UI Elements (Single Order)**:
        - Forms for Sender, Recipient, and Package details.
        - "Get Rates" button to see prices from different carriers.
        - "Book Order" button after selecting a carrier service.
    - **UI Elements (Bulk Order)**:
        - A link to download a CSV/Excel template.
        - An upload button for the completed file.
        - "Confirm and Book All" button after the file is validated.
    - **Backend**: `orders.createSingle`, `orders.createBulk`
8. **All Orders (Historical View)**
    - **UI Elements**:
        - A table of all past and current orders.
        - Columns: Order Date, AWB No., Recipient, Carrier, Status, Cost.
        - Filters by Carrier, Status, and Date Range.
        - Action buttons for each order: "Track" and "Print Label".
    - **Backend**: `orders.getAllMyOrders`
9. **Label Print**
    - **UI Elements**:
        - This is an action, typically a "Print Label" button within the "All Orders" page for each shipment.
    - **Action**:
        - Triggers a download or opens a new tab with the shipping label in PDF format.
    - **Backend**: `orders.printLabel`
10. **Tracking Dashboard**
    - **UI Elements**:
        - A dashboard view showing cards for all active shipments.
        - Each card displays AWB No., current status, and ETA.
        - Clicking a card reveals a detailed tracking timeline.
    - **Backend**: `tracking.getMyShipmentStatus`
11. **Support**
    - **UI Elements**:
        - A list of previously created support tickets with their status.
        - "Create New Ticket" button.
        - A form with Subject and Description fields for new tickets.
        - A view to see the conversation history for a specific ticket.
    - **Backend**: `support.getMyTickets` to list, `support.createTicket` to create a new one.
12. **Sales Report**
    - **UI Elements**:
        - Inputs to select a date range.
        - "Generate & Export" button.
    - **Action**:
        - Downloads an Excel file with detailed sales data for the selected period.
    - **Backend**: `reports.getSalesData`
13. **Quick Action Buttons**
    - **UI Elements**:
        - Prominently displayed buttons on the client's main dashboard.
        - Buttons include: "Book an Order," "Recharge Wallet," "Track a Shipment," and "Rate Calculator."
    - **Action**:
        - Acts as shortcuts to navigate to the respective pages.

---

## Admin Pages

1. **User Control**
    - **UI Elements**:
        - A table of all clients and employees with columns for Name, Email, User Type, and Status.
        - Filters by user type and status.
        - Action buttons per user: "Activate/Deactivate," "Modify Details," "Manage Wallet."
    - **Backend**: `users.getAll`, `users.updateStatus`, `users.updateDetails`
2. **Employee Management**
    - **UI Elements**:
        - A table of all employees with their assigned roles.
        - "Add New Employee" button.
        - A form to add or edit employee details and assign roles/permissions.
    - **Backend**: `users.getAll` (filtered for employees), `users.assignRole`, `auth.createEmployee`
3. **Wallet Management**
    - **UI Elements**:
        - A search bar to find a user by email or client ID.
        - Once a user is selected, it displays their current balance.
        - Inputs to manually add or deduct funds, with a field for the reason.
        - A view of the selected user's transaction history.
    - **Backend**: `wallet.adjustBalance`, `wallet.getTransactions`
4. **Payment Verification**
    - **UI Elements**:
        - A queue of manually uploaded payment proofs that are pending verification.
        - Action buttons for each payment: "Verify" or "Reject."
    - **Backend**: `wallet.verifyPayment`, `wallet.getPendingPayments`
5. **Revenue Dashboard**
    - **UI Elements**:
        - Dashboard with key metrics: Total Revenue, Total Shipments, New Clients.
        - Visual charts for revenue trends over time and revenue breakdown by carrier.
        - "Export Revenue Data" button.
    - **Backend**: `analytics.getRevenueSummary`
6. **All Orders**
    - **UI Elements**:
        - A comprehensive table of every order on the platform.
        - Columns: AWB No., Client, Carrier, Status, Date, Cost, etc.
        - Filters by Client, Carrier, Status, and Date.
    - **Backend**: `orders.getAll`
7. **Tracking Dashboard**
    - **UI Elements**:
        - A real-time overview (map or list) of all shipments currently in transit.
        - Ability to filter by carrier and status.
        - Highlights shipments that are delayed or have exceptions.
    - **Backend**: `tracking.getAllActiveShipments`
8. **Order Approval / Rejection**
    - **UI Elements**:
        - A queue of orders with the status "Pending Approval."
        - Action buttons for each order: "Approve" or "Reject" (with a reason).
        - Bulk action capabilities to approve/reject multiple orders at once.
    - **Backend**: `orders.approve`, `orders.reject`, `orders.getPendingApproval`
9. **Label Download**
    - **UI Elements**:
        - This is an action within the "All Orders" page.
        - Allows downloading a single label or selecting multiple orders to download labels in bulk.
    - **Backend**: `orders.downloadLabel`
10. **Rate Management**
    - **UI Elements**:
        - A table of all shipping rates configured in the system.
        - "Add New Rate" button.
        - A form to add or edit rates based on carrier, weight, dimensions, and zones.
        - Capability to set user-specific rate adjustments.
    - **Backend**: `rates.getAll`, `rates.create`, `rates.update`
11. **Support Management**
    - **UI Elements**:
        - A dashboard showing all support tickets.
        - Filters by status, priority, and assigned employee.
        - Ability to view a ticket, assign it to an employee, and update its status.
    - **Backend**: `support.getAllTickets`, `support.updateTicketStatus`, `support.assignTicket`
12. **Universal Search Bar**
    - **UI Elements**:
        - A persistent search bar in the admin panel header.
    - **Action**:
        - Allows searching across the entire platform using AWB/LR No., Mobile Number, Name, or Client ID, with categorized results.
    - **Backend**: `search.universalSearch`