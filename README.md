# snake_bevy_0.6_egui

Hello, this is a try to integrate a bevy 0.6 game inside egui thanks to bevy_egui. A kind of memo / proof of concept on Bevy 0.6.
The example game is snake from https://github.com/marcusbuffett/bevy_snake , version i found elegant.

It does compile BUT panicks:



cargo run RUST_BACKTRACE=1
warning: unused variable: `entity`
  --> src/app_state.rs:14:9
   |
14 |     for entity in entities.iter() {
   |         ^^^^^^ help: if this is intentional, prefix it with an underscore: `_entity`
   |
   = note: `#[warn(unused_variables)]` on by default

warning: unused variable: `commands`
  --> src/app_state.rs:13:32
   |
13 | pub fn game_state_teardown(mut commands: Commands, entities: Query<Entity>) {
   |                                ^^^^^^^^ help: if this is intentional, prefix it with an underscore: `_commands`

warning: unused variable: `app`
   --> src/bevy_minigames/snake.rs:281:18
    |
281 | pub fn add_snake(app: &mut App) {
    |                  ^^^ help: if this is intentional, prefix it with an underscore: `_app`

warning: variable does not need to be mutable
  --> src/app_state.rs:13:28
   |
13 | pub fn game_state_teardown(mut commands: Commands, entities: Query<Entity>) {
   |                            ----^^^^^^^^
   |                            |
   |                            help: remove this `mut`
   |
   = note: `#[warn(unused_mut)]` on by default

warning: function is never used: `game_state_teardown`
  --> src/app_state.rs:13:8
   |
13 | pub fn game_state_teardown(mut commands: Commands, entities: Query<Entity>) {
   |        ^^^^^^^^^^^^^^^^^^^
   |
   = note: `#[warn(dead_code)]` on by default

warning: constant is never used: `PX_SIZE_OF_LEFT_PANEL`
  --> src/app_state.rs:19:1
   |
19 | pub const PX_SIZE_OF_LEFT_PANEL: f32 = 110.0;
   | ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

warning: `ui_snake_6` (lib) generated 6 warnings
    Finished dev [unoptimized + debuginfo] target(s) in 0.07s
     Running `target/debug/ui_snake_6_app RUST_BACKTRACE=1`
2022-01-24T18:58:16.350910Z  WARN winit::platform_impl::platform::x11::util::randr: XRandR reported that the display's 0mm in size, which is certifiably insane    
2022-01-24T18:58:16.351411Z  INFO winit::platform_impl::platform::x11::window: Guessed window scale factor: 1    
MESA-INTEL: warning: Performance support disabled, consider sysctl dev.i915.perf_stream_paranoid=0

MESA-INTEL: warning: Performance support disabled, consider sysctl dev.i915.perf_stream_paranoid=0

2022-01-24T18:58:16.435875Z  INFO bevy_render::renderer: AdapterInfo { name: "NVIDIA GeForce RTX 2060", vendor: 4318, device: 7957, device_type: DiscreteGpu, backend: Vulkan }
thread 'main' panicked at 'called `Result::unwrap()` on an `Err` value: SetLoggerError(())', /home/Me/.cargo/registry/src/github.com-1ecc6299db9ec823/bevy_log-0.6.0/src/lib.rs:92:27
note: run with `RUST_BACKTRACE=1` environment variable to display a backtrace

  
  
  
  

Hhheeeellppppp



usefull link :  https://bevyengine.org/learn/book/migration-guides/0.5-0.6/
