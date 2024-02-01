<script>
    import { writable } from 'svelte/store';
    // Store to manage the state of the sidebar (open/closed)
    export const sidebarOpen = writable(false);
    // Function to toggle the sidebar state
    export function toggleSidebar() {
      sidebarOpen.update(value => !value);
    }
</script>

<style>
  /* Sidebar styling */
  .sidebar {
    width: 250px;
    height: auto;
    background-color: blue;
    color: #fff;
    /* padding: 20px; */
    transition: transform 0.3s ease-in-out;
    display: flex;
    flex-direction: column;
    align-items: center;
    /* Add shadow for depth */
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  }

  /* Responsive styles */
  @media (max-width: 768px) {
    .sidebar {
      position: fixed;
      top: 0;
      left: -250px;
      z-index: 1000;
    }

    /* Display sidebar when open */
    .sidebar.open {
      transform: translateX(0);
    }
  }

  /* Additional styling for the SVG icon */
  .home-icon {
    fill: #fff;
    margin-bottom: 10px;
  }

  /* Button styling */
  .toggle-button {
    position: absolute;
    top: 20px;
    right: 20px;
    background-color: transparent;
    border: none;
    color: #fff;
    cursor: pointer;
    z-index: 1001; /* Ensure button is above sidebar */
  }
  .sidebar-item svg {
    width: 20px;
    height: 20px;
    margin-right: 10px;
  }

</style>

<div style="display:flex; justify-content: flex-start;" class="sidebar {sidebarOpen ? 'open' : ''}">
    <!-- Sidebar content -->
    <div class="sidebar-item" style="display: flex; align-items: center; "> <!-- Apply inline CSS -->
      <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"  style="width: 20px;"> <!-- Apply inline width -->
          <path stroke-linecap="round" stroke-linejoin="round" d="m2.25 12 8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
      </svg>
      <h4 class="inline-block" style="margin-left: 70px; ">Home</h4> <!-- Adjust margin to position "Home" on the left -->
    </div>

    <hr style="color: white; width:250px;">
  <div style="margin-right: 130px;">Getting Started</div>

  <!-- ------------------------------------------------------------------------------------------------- -->
  <div class="sidebar-item" style="display: flex; align-items: center;"> <!-- Apply inline CSS -->
    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" style="width: 20px;" class="w-6 h-6">
        <path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75 11.25 15 15 9.75M21 12a9 9 0 1 1-18 0 9 9 0 0 1 18 0Z" />
      </svg>
    <h4 class="inline-block" style="margin-left: 70px; ">Requirements</h4> <!-- Adjust margin to position "Home" on the left -->
  </div>

  <!-- ------------------------------------------------------------------------------------------------- -->
  <div class="sidebar-item" style="display: flex; align-items: center;"> <!-- Apply inline CSS -->
    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"  style="width: 20px;"> <!-- Apply inline width -->
        <path stroke-linecap="round" stroke-linejoin="round" d="m2.25 12 8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
    </svg>
    <h4 class="inline-block" style="margin-left: 70px; ">Installation</h4> <!-- Adjust margin to position "Home" on the left -->
  </div>
    

  <!-- ------------------------------------------------------------------------------------------------- -->
  <div class="sidebar-item" style="display: flex; align-items: center;"> <!-- Apply inline CSS -->
    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" style="width: 20px;" class="w-6 h-6">
        <path stroke-linecap="round" stroke-linejoin="round" d="M9 8.25H7.5a2.25 2.25 0 0 0-2.25 2.25v9a2.25 2.25 0 0 0 2.25 2.25h9a2.25 2.25 0 0 0 2.25-2.25v-9a2.25 2.25 0 0 0-2.25-2.25H15m0-3-3-3m0 0-3 3m3-3V15" />
      </svg>
    <h4 class="inline-block" style="margin-left: 70px; ">Upgrade</h4> <!-- Adjust margin to position "Home" on the left -->
  </div>
    

  <!-- ------------------------------------------------------------------------------------------------- -->
  <div class="sidebar-item" style="display: flex; align-items: center;"> <!-- Apply inline CSS -->
    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" style="width: 20px;" class="w-6 h-6">
        <path stroke-linecap="round" stroke-linejoin="round" d="M15.362 5.214A8.252 8.252 0 0 1 12 21 8.25 8.25 0 0 1 6.038 7.047 8.287 8.287 0 0 0 9 9.601a8.983 8.983 0 0 1 3.361-6.867 8.21 8.21 0 0 0 3 2.48Z" />
        <path stroke-linecap="round" stroke-linejoin="round" d="M12 18a3.75 3.75 0 0 0 .495-7.468 5.99 5.99 0 0 0-1.925 3.547 5.975 5.975 0 0 1-2.133-1.001A3.75 3.75 0 0 0 12 18Z" />
      </svg>
    <h4 class="inline-block" style="margin-left: 70px; ">Release Notes</h4> <!-- Adjust margin to position "Home" on the left -->
  </div>
    
  <hr style="color: white; width:250px;">
  <div style="margin-right: 130px;">User Goods</div>

  <!-- ------------------------------------------------------------------------------------------------ -->

  <!-- ------------------------------------------------------------------------------------------------- -->
  <div class="sidebar-item" style="display: flex; align-items: center;"> <!-- Apply inline CSS -->
    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"  style="width: 20px;"> <!-- Apply inline width -->
        <path stroke-linecap="round" stroke-linejoin="round" d="m2.25 12 8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
    </svg>
    <h4 class="inline-block" style="margin-left: 70px; ">pages</h4> <!-- Adjust margin to position "Home" on the left -->
  </div>

  <!-- ------------------------------------------------------------------------------------------------- -->
  <div class="sidebar-item" style="display: flex; align-items: center;"> <!-- Apply inline CSS -->
    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"  style="width: 20px;"> <!-- Apply inline width -->
        <path stroke-linecap="round" stroke-linejoin="round" d="m2.25 12 8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
    </svg>
    <h4 class="inline-block" style="margin-left: 70px; ">Editors</h4> <!-- Adjust margin to position "Home" on the left -->
  </div>
    

  <!-- ------------------------------------------------------------------------------------------------- -->
  <div class="sidebar-item" style="display: flex; align-items: center;"> <!-- Apply inline CSS -->
    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"  style="width: 20px;"> <!-- Apply inline width -->
        <path stroke-linecap="round" stroke-linejoin="round" d="m2.25 12 8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
    </svg>
    <h4 class="inline-block" style="margin-left: 70px; ">Media Assets</h4> <!-- Adjust margin to position "Home" on the left -->
  </div>
 <hr style="color: white; width:250px;">


 <!-- ------------------------------------------------------------------------------------------------- -->

  <!-- ------------------------------------------------------------------------------------------------- -->
  <div class="sidebar-item" style="display: flex; align-items: center;"> <!-- Apply inline CSS -->
    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"  style="width: 20px;"> <!-- Apply inline width -->
        <path stroke-linecap="round" stroke-linejoin="round" d="m2.25 12 8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
    </svg>
    <h4 class="inline-block" style="margin-left: 70px; ">Authentication</h4> <!-- Adjust margin to position "Home" on the left -->
  </div>
    

  <!-- ------------------------------------------------------------------------------------------------- -->
  <div style="display: flex; align-items: center;"> <!-- Apply inline CSS -->
    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"  style="width: 20px;"> <!-- Apply inline width -->
        <path stroke-linecap="round" stroke-linejoin="round" d="m2.25 12 8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
    </svg>
    <h4 class="inline-block" style="margin-left: 70px; ">Locations</h4> <!-- Adjust margin to position "Home" on the left -->
  </div>
    
  <hr style="color: white; width:250px;">
  <div style="margin-right: 130px;">User Goods</div>

  <!-- ------------------------------------------------------------------------------------------------ -->

  <!-- ------------------------------------------------------------------------------------------------- -->
  <div style="display: flex; align-items: center;"> <!-- Apply inline CSS -->
    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"  style="width: 20px;"> <!-- Apply inline width -->
        <path stroke-linecap="round" stroke-linejoin="round" d="m2.25 12 8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
    </svg>
    <h4 class="inline-block" style="margin-left: 70px; ">Search Engines</h4> <!-- Adjust margin to position "Home" on the left -->
  </div>

  <!-- ------------------------------------------------------------------------------------------------- -->
  <div style="display: flex; align-items: center;"> <!-- Apply inline CSS -->
    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"  style="width: 20px;"> <!-- Apply inline width -->
        <path stroke-linecap="round" stroke-linejoin="round" d="m2.25 12 8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
    </svg>
    <h4 class="inline-block" style="margin-left: 70px; ">Storage</h4> <!-- Adjust margin to position "Home" on the left -->
  </div>
    

  <!-- ------------------------------------------------------------------------------------------------- -->
  <div style="display: flex; align-items: center;"> <!-- Apply inline CSS -->
    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"  style="width: 20px;"> <!-- Apply inline width -->
        <path stroke-linecap="round" stroke-linejoin="round" d="m2.25 12 8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25" />
    </svg>
    <h4 class="inline-block" style="margin-left: 70px; ">Users, Groups and Permissions</h4> <!-- Adjust margin to position "Home" on the left -->
  </div>

  
    <!-- Toggle button -->
    <button class="toggle-button" on:click={toggleSidebar}>Toggle Sidebar</button>
</div>
