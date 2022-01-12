<script>
	import {
        Navbar,
        NavbarBrand,
        Nav,
        NavItem,
        NavLink,
        Dropdown,
        DropdownToggle,
        DropdownMenu,
        DropdownItem
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
        <Dropdown nav inNavbar>
            <DropdownToggle nav caret>Portfolio</DropdownToggle>
            <DropdownMenu dark>
                <DropdownItem>Classes.gg</DropdownItem>
                <DropdownItem>Dragonfire</DropdownItem>
                <DropdownItem>Housyn</DropdownItem>
            </DropdownMenu>
        </Dropdown>
    </Nav>
</Navbar>

<style>
    :global(.navbar) {
        background-color: #343a40;
    }
</style>