# IDEA9103 Week 8 Quiz
## Part 1: Imaging Technique Inspiration
Imaging Technique: Long-exposure light accumulation / temporal traces
I've been looking at Hiroshi Sugimoto's Seascapes series and I think it's really interesting how he uses super long exposure times to basically erase all the details from the ocean. You end up with just this thin line where sky meets water — it feels very still and almost unreal, like looking at a memory rather than a photo.

I want to try something similar in my project but through code. Instead of a camera, I'm thinking of using particles that follow the mouse and leave behind glowing trails. The key is not clearing the canvas each frame — instead I'd overlay a very low-alpha black rectangle so previous frames fade slowly. This way the movement leaves a trace, almost like the code is "remembering" what happened.

I think this works well for creative coding because things like frame persistence, alpha blending and noise-based movement can replicate that same feeling of time passing — but with the extra layer of interactivity that photography can't offer.

### Reference Images
<img width="757" height="726" alt="Screenshot 2026-05-08 at 10 11 36 am" src="https://github.com/user-attachments/assets/3fda7fd2-2201-46d6-86f1-d710f0ed50a8" />
<img width="684" height="581" alt="Screenshot 2026-05-08 at 9 36 39 am" src="https://github.com/user-attachments/assets/63fc3462-8943-463d-8ed5-76305f0570ea" />
<img width="741" height="581" alt="Screenshot 2026-05-08 at 9 33 06 am" src="https://github.com/user-attachments/assets/7b1b9360-dbd3-471f-bc01-9116616d4308" />


## Part 2: Coding Technique Exploration
Coding Technique: Frame persistence + Perlin noise flow field
The main idea here is pretty simple — instead of calling background() every frame to clear the canvas, you draw a semi-transparent black rectangle over everything (fill(0, 0, 0, 10)). This means previous frames don't disappear immediately but slowly fade out, creating trailing light effects that look like long-exposure photography.

For the movement itself, I'd use a Perlin noise flow field to control particle direction. Basically you sample noise(x, y, t) at each position on a grid, convert it to an angle, and each particle moves along that angle. This creates really organic, drifting motion — way more interesting than just bouncing particles around.

Combined with blendMode(ADD) for that glow effect, this directly connects to the imaging technique from Part 1. It's all stuff we've covered in class (particles, noise, alpha) so it's achievable but the output actually looks like media art rather than a basic coding exercise.

### Example Screenshot
<img width="754" height="720" alt="Screenshot 2026-05-08 at 10 11 07 am" src="https://github.com/user-attachments/assets/42bf660d-34c4-41ac-af96-0eb0208cecf9" />
<img width="742" height="617" alt="Screenshot 2026-05-08 at 10 11 23 am" src="https://github.com/user-attachments/assets/45e2c5ff-a58b-49e1-a824-c7c2ece1f362" />
![Uploading Screenshot 2026-05-08 at 10.11.36 am.png…]()


### Example Link
https://p5js.org/examples/repetition-noise/
https://p5js.org/examples/math-and-physics-smoke-particle-system/
