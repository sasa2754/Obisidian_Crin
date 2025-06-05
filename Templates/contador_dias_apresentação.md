<%*
function getBusinessDaysUntil(targetDate) {
  const today = new Date();
  const endDate = new Date(targetDate);
  let count = 0;

  today.setHours(0, 0, 0, 0);
  endDate.setHours(0, 0, 0, 0);

  let current = new Date(today);

  while (current < endDate) {
    const day = current.getDay();
    if (day !== 0 && day !== 6) {
      count++;
    }
    current.setDate(current.getDate() + 1);
  }

  return count;
}

const dias = getBusinessDaysUntil("2025-06-26");
t.print("Faltam " + dias + " dias úteis até 26 de junho de 2025! 📅")
%>
