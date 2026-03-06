<script lang="ts">
  const envVars = {
    'VITE_APP_NAME': import.meta.env.VITE_APP_NAME,
    'VITE_API_URL': import.meta.env.VITE_API_URL,
    'VITE_APP_VERSION': import.meta.env.VITE_APP_VERSION,
    'VITE_ENVIRONMENT': import.meta.env.VITE_ENVIRONMENT || 'development',
    'VITE_SUPABASE_URL': import.meta.env.VITE_SUPABASE_URL || 'https://test-svelte.supabase.co',
    'VITE_SUPABASE_ANON_KEY': import.meta.env.VITE_SUPABASE_ANON_KEY || 'Ztest-svelte-anon-key',
  };
</script>

<main>
  <h1>Svelte Environment Variables</h1>

  <div class="env-container">
    <p class="description">
      Below are the environment variables loaded from the .env file: addasx asxas
    </p>

    <div class="env-list">
      {#each Object.entries(envVars) as [key, value]}
        <div class="env-item">
          <span class="env-key">{key}:</span>
          <h5 class="env-value">{value || 'undefined'}</h5>
        </div>
      {/each}
    </div>

    <div class="note">
      <strong>Note:</strong> In Vite, environment variables must be prefixed with <code>VITE_</code> to be exposed to the client-side code.
    </div>
  </div>
</main>

<style>
  main {
    max-width: 800px;
    margin: 0 auto;
    padding: 2rem;
  }

  h1 {
    font-size: 2.5em;
    margin-bottom: 1.5rem;
    color: #333;
  }

  .env-container {
    background: #f5f5f5;
    border-radius: 8px;
    padding: 2rem;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  }

  .description {
    margin-bottom: 1.5rem;
    color: #666;
    font-size: 1.1em;
  }

  .env-list {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    margin-bottom: 1.5rem;
  }

  .env-item {
    background: white;
    padding: 1rem;
    border-radius: 4px;
    display: flex;
    gap: 0.5rem;
    align-items: center;
    border-left: 4px solid #646cff;
  }

  .env-key {
    font-weight: 600;
    color: #333;
    min-width: 250px;
  }

  .env-value {
    color: #646cff;
    font-family: 'Courier New', monospace;
    background: #f0f0f0;
    padding: 0.25rem 0.5rem;
    border-radius: 4px;
    word-break: break-all;
    flex: 1;
  }

  .note {
    background: #fff3cd;
    border: 1px solid #ffc107;
    border-radius: 4px;
    padding: 1rem;
    color: #856404;
  }

  .note code {
    background: #ffeaa7;
    padding: 0.2rem 0.4rem;
    border-radius: 3px;
    font-family: 'Courier New', monospace;
  }

  @media (prefers-color-scheme: light) {
    h1 {
      color: #213547;
    }
  }

  @media (max-width: 640px) {
    .env-item {
      flex-direction: column;
      align-items: flex-start;
    }

    .env-key {
      min-width: auto;
    }
  }
</style>
