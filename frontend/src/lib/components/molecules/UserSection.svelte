<script lang="ts">
    import Avatar from "$lib/components/atoms/Avatar.svelte";
    import Button from "$lib/components/atoms/Button.svelte";

    /** @type {{ user?: { name: string, email: string, avatar?: string } }} */
    let { user } = $props();
</script>

<div class="user-section">
    {#if user}
        <Avatar src={user.avatar} alt={user.name} />
        <div class="user-info">
            <p class="name">{user.name}</p>
            <p class="email">{user.email}</p>
        </div>
        <Button variant="ghost" size="sm">Logout</Button>
    {:else}
        <div class="user-info">
            <p class="placeholder">No has iniciado sesión</p>
        </div>
        <Button variant="primary" size="sm">Login</Button>
    {/if}
</div>

<style>
    .user-section {
        display: flex;
        align-items: center;
        gap: var(--spacing-md);
        padding: var(--spacing-md);
        background-color: var(--color-white);
        border-radius: var(--radius-lg);
        box-shadow: var(--shadow-sm);
        border: 1px solid var(--color-border);
    }

    .user-info {
        flex: 1;
    }

    .name {
        font-weight: 500;
        color: var(--color-text);
        margin: 0;
    }

    .email {
        font-size: 0.875rem;
        color: var(--color-text-light);
        margin: 0;
    }

    .placeholder {
        font-size: 0.875rem;
        color: var(--color-text-light);
        margin: 0;
    }
</style>
