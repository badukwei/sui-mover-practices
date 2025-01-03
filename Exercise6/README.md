# Package

0xfe6547fbe5b84f9638e88157c5b641a5d059119cb7a8283ff4a53c49b211d318

# Exercise 6

## Fail

```
sui client ptb \
--assign world @0x068d5ff571b34d02fbe1cd0a8f748d496e3f626a4833bb238900e090343482e4 \
--assign crew @0x28aec632ff120da39cff30a63dbcda44f39928efb087a5ef79b0d4b71f69fd95 \
--assign simple_nft @0x85ae44cd7d3ce48be1f731ca9a24eb2b91238181f03e61fa4fde11d3b6a21cbc \
--assign kiosk @0x90df9555659e8d1fe6a57e8c1f1c67a2a093b0ba3ae3de23da2a46d3d3b4b599 \
--assign kiosk_cap @0x4854d1d173f8b13d7449e6081159a543d3dfaa3f466f7c80a0b1f73ac561de00 \
--assign tails @0xc43ba72aba8c53be3285efb99a14e579167186d2e4b5e9a653d3ca6dcfc9df6e \
--move-call 0x2::kiosk::borrow"<0x27321bc52766f3ed3f809524ca0149bdbbf01f7f18bdccc261eab2dc5fa14589::mover_nft::Tails>" kiosk kiosk_cap tails --assign tails_ref \
--move-call 0xfe6547fbe5b84f9638e88157c5b641a5d059119cb7a8283ff4a53c49b211d318::exercise::goal world crew simple_nft tails_ref
```

Error executing transaction : InvalidPublicFunctionReturnType { idx: 0 } in command 0

### STEP.1 Mint Simple NFT

https://github.com/SuiMover/Sui-Mover-2024-2/blob/main/Lesson5/README.md#exercise-5-mint-your-simple-nft

### STEP.2 Mint Mover Tails

https://github.com/SuiMover/Sui-Mover-2024-2/blob/main/Lesson6/README.md#mint

### STEP.3

https://github.com/SuiMover/Sui-Mover-2024-2/blob/main/Lesson6/README.md#mint

## Success

```
sui client ptb \
--assign world @0x068d5ff571b34d02fbe1cd0a8f748d496e3f626a4833bb238900e090343482e4 \
--assign crew @0x7f622521a0c0c2bf61f99eaede66375ee01f60fec932a61c4cf32626b0e81165 \
--assign simple_nft @0x395dcd44158822f4a6375debdd25acd2de887203f86ad015aa6fa7bcb984d24b \
--assign kiosk @0x1fc79bb3ce7e50ae4425d450e00b4575b5376588f8e3b7e47baf25ae37f80bca \
--assign kiosk_cap @0xcd7e76c75d3639bb8eee742d10163e1bb09013183912e720e79b2825e893a22f \
--assign tails @0x8c318b3af20342e266f7fb266a5605ef84f84fb1eebc944c0efc0c0a3d3e126b \
--move-call 0x2::kiosk::borrow_val"<0x27321bc52766f3ed3f809524ca0149bdbbf01f7f18bdccc261eab2dc5fa14589::mover_nft::Tails>" kiosk kiosk_cap tails --assign result \
--move-call 0xfe6547fbe5b84f9638e88157c5b641a5d059119cb7a8283ff4a53c49b211d318::exercise::goal_2 world crew simple_nft result.0 --assign return_nft \
--move-call 0x2::kiosk::return_val"<0x27321bc52766f3ed3f809524ca0149bdbbf01f7f18bdccc261eab2dc5fa14589::mover_nft::Tails>" kiosk return_nft result.1
```
