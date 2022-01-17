<script>
	import {
        Navbar,
        NavbarBrand,
        Nav,
        NavItem,
        NavLink,
    } from 'sveltestrap';
</script>


<Navbar dark expand="md">
    <NavbarBrand href="/">
        <img src="logo.png" alt="logo" width="38" height="30">
    </NavbarBrand>
    <Nav class="me-auto" navbar >
        <NavItem>
            <NavLink href="#about/">About</NavLink>
        </NavItem>
    </Nav>
</Navbar>

<style>
    :global(.navbar) {
        background-color: #343a40;
    }
</style>