# LeetCode Practice Picker


A lightweight, browser-based question generator for coding interview preparation. Pick random LeetCode problems, track which ones you've completed, and prioritize questions you want to revisit—all from a single HTML file.
Features
- 413 unique questions organized by algorithm and data structure topics. Questions that appear in multiple categories are tracked as one problem.
- Random practice sessions: Generate 1–30 questions at a time, across all topics or within a selected category.
- Progress tracking: Mark each problem as Not started, Done, or Need practice.
- Weighted review: Give Need practice problems a higher chance of appearing, adjustable from 1× to 10× (default: 3×).
- Avoid immediate repeats: When enough alternatives exist, the next generated batch avoids problems from the previous batch.
- Browse and search: Filter the full question list by keyword, category, and status.
- LeetCode links: Click a question title to open its LeetCode problem page.
- Local progress saving: Changes are automatically saved in your browser using localStorage.
- Backup and restore: Export your progress as a JSON file and import it later.
Getting Started
1. Download or clone this repository.
2. Open leetcode_practice_picker.html in a web browser.
3. Choose a topic (or All topics), select the number of questions, and click Generate.
4. After practicing, update each question's status. Your changes are saved automatically.
No installation, build step, server, or account is required. The picker itself works offline; opening a problem on LeetCode requires internet access.
How Question Selection Works
Status	Default selection behavior
Not started	Eligible with normal weight (1×)
Done	Excluded from generation
Need practice	Eligible with increased weight (3× by default)


For each question in a batch, the picker randomly chooses from the eligible questions using their selection weights, then removes that question from the current batch's pool. This means a question cannot appear twice within the same generated batch. The picker also avoids the previous batch's questions when enough other eligible questions are available.

You can adjust the review multiplier from 1× to 10×. For example, at 3×, a Need practice question has three times the selection weight of a Not started question—not a guaranteed appearance. You can also enable Include done questions to bring completed questions back into the random pool.
Saving Your Progress
Progress is stored in your browser's localStorage. It normally survives refreshes, browser restarts, and laptop restarts, but it does not automatically sync across browsers, devices, or browser profiles. Local-file (file://) storage behavior can vary by browser; moving or renaming the HTML file may affect access to existing saved data.

To keep a reliable backup:
1. Click Export progress (.json) to save your question statuses and settings.
2. Keep the downloaded leetcode-practice-progress.json somewhere safe.
3. To restore, click Import progress and select that file.
Reset progress clears your saved question statuses. Export a backup first if you might want to recover them.
Technology
- HTML, CSS, and vanilla JavaScript
- Browser localStorage for persistence
- JSON for importing and exporting progress
- No external dependencies or backend
Limitations
- Progress is local to the browser rather than tied to an account.
- The question list is embedded in the HTML file; adding new questions requires editing the file.
- A LeetCode link may not resolve if its URL slug differs from the title-generated slug.
Possible Future Improvements
- Cloud synchronization across devices
- A way to add or edit questions through the interface
- Practice history and spaced-repetition scheduling
- Difficulty filters and interview-focused question sets
Built for consistent coding interview practice, with extra attention to problems that need another attempt.

The questions are picked from https://docs.google.com/spreadsheets/d/1EEYzyD_483B-7CmWxsJB_zycdv4Y5dxnzcoEQtaIfuk/edit?gid=329533698#gid=329533698