# angry os 😠

**🏗 TODO**:

- [ ] Implement the rest types for the EFI_SYSTEM_TABLE
- [ ] Implement the rest types and functions for the EFI_BOOT_SERVICES

**📝 Read**:

- https://sandpile.org/x86/initial.htm
- https://github.com/rust-lang/rust/pull/56769/files
- https://lwn.net/Articles/632528/
- https://en.wikipedia.org/wiki/Unified_Extensible_Firmware_Interface
- https://uefi.org/sites/default/files/resources/ACPI_Spec_6_3_A_Oct_6_2020.pdf

**🧱 How to build**:  
Just run: ./run.sh. To exit use CTRL-A + X

**🏎 Roadmap**:

- Considerations
  - RAM should be more than > 4Gb
  - NO LEGACY!
- UEFI kernel
  - PXE boot (via internet)
  - UEFI as loader
  - UEFI for memory map and stdout
- Non-shared memory kernel
  - Rust-style kernel
  - Memory can be shared between cores if it is read-only
  - Mutable memory is exclusive to one core
    - Cache coherency
    - No locks
  - Page tables don't need locks
  - No TLB shootdowns
- Soft reboots
  - Bootloader/Loader

Useful commands:

- objdump -M intel -d target/x86_64-unknown-uefi/debug/angry_os.efi
