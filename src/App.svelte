<script>
    import Sidebar from './Sidebar.svelte';
    export let name;
  </script>
  <style>
	
    /* Global styles can be included here */
    /* Your existing styles remain unchanged */
    /* Add specific styles for the Sidebar if needed */
    @media (min-width: 640px) {
      .main-content {
        max-width: none;
      }
    }



  </style>
  <main>
    <!-- Include the Sidebar component -->
    <Sidebar />
    <!-- Your existing content remains unchanged -->
  </main>
