module MyModule::PharmacyLedger {

    use std::signer;
    use std::string;
    use std::vector;

    /// Struct representing a verified pharmacy
    struct Pharmacy has key, store {
        name: string::String,
        license_id: string::String,
    }

    /// Function to register a verified pharmacy
    public fun register_pharmacy(admin: &signer, name: string::String, license_id: string::String) {
        let addr = signer::address_of(admin);

        assert!(!exists<Pharmacy>(addr), 1); // Prevent re-registration

        let pharmacy = Pharmacy {
            name,
            license_id,
        };
        move_to(admin, pharmacy);
    }

    /// Function to check if an address is a registered pharmacy
    public fun is_pharmacy_verified(pharmacy_addr: address): bool {
        exists<Pharmacy>(pharmacy_addr)
    }
}
